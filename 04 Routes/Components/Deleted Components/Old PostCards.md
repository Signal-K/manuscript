---
tags:
  - Post
  - PostCards
  - SSG-90
---
# By Anomaly
```tsx
'use client';

  

import React, { useEffect, useState } from 'react';

import { useSession, useSupabaseClient } from '@supabase/auth-helpers-react';

import { DiscoveryCardSingle } from './Classification';

  

interface DiscoveryCardsByUserAndAnomalyProps {

anomalyId: number;

};

  

export function DiscoveryCardsByUserAndAnomaly({ anomalyId }: DiscoveryCardsByUserAndAnomalyProps) {

const supabase = useSupabaseClient();

const session = useSession();

const [classifications, setClassifications] = useState<any[]>([]);

const [totalClassifications, setTotalClassifications] = useState<number | null>(null);

const [userClassificationsCount, setUserClassificationsCount] = useState<number | null>(null);

const [loading, setLoading] = useState<boolean>(true);

const [error, setError] = useState<string | null>(null);

  

useEffect(() => {

const fetchClassifications = async () => {

setLoading(true);

setError(null);

  

// Check if session is available

if (!session?.user?.id) {

setError('No user session found.');

setLoading(false);

return;

}

  

try {

// Fetch total classifications for this anomaly

const { count: totalCount, error: totalError } = await supabase

.from('classifications')

.select('id', { count: 'exact' })

.eq('anomaly', anomalyId);

  

if (totalError) {

console.error('Error fetching total classifications:', totalError);

throw totalError;

};

  

setTotalClassifications(totalCount);

  

// Fetch the number of classifications the user has made for this anomaly

const { count: userCount, error: userError } = await supabase

.from('classifications')

.select('id', { count: 'exact' })

.eq('author', session.user.id)

.eq('anomaly', anomalyId);

  

if (userError) {

console.error('Error fetching user classifications count:', userError);

throw userError;

};

  

setUserClassificationsCount(userCount);

  

// Fetch the actual classification data for the user

const { data, error: classificationsError } = await supabase

.from('classifications')

.select('id')

.eq('author', session.user.id)

.eq('anomaly', anomalyId);

  

if (classificationsError) {

console.error('Error fetching classifications data:', classificationsError);

throw classificationsError;

}

  

setClassifications(data);

} catch (error) {

console.error('Error fetching classifications:', error);

setError('Failed to load classifications.');

} finally {

setLoading(false);

}

};

  

fetchClassifications();

}, [anomalyId, supabase, session?.user?.id]);

  

if (loading) return <p>Loading...</p>;

if (error) return <p>{error}</p>;

  

return (

<div className="flex flex-col space-y-4">

{/* Display total classifications and user-specific count */}

<div className="mb-4">

<p>Total classifications for this anomaly: {totalClassifications ?? 'N/A'}</p>

<p>Your classifications for this anomaly: {userClassificationsCount ?? 'N/A'}</p>

</div>

  

{classifications.length === 0 ? (

<p>No classifications found for this anomaly by user</p>

) : (

classifications.map((classification) => (

<DiscoveryCardSingle key={classification.id} classificationId={classification.id} />

))

)}

</div>

);

};
```


# By Active Planet
```tsx
'use client';

  

import React, { useEffect, useState } from 'react';

import { useSupabaseClient } from '@supabase/auth-helpers-react';

import { DiscoveryCardSingle } from './Classification';

  

interface DiscoveryCardsByActivePlanetProps {

activePlanet: number;

};

  

export function DiscoveryCardsByActivePlanet({ activePlanet }: DiscoveryCardsByActivePlanetProps) {

const supabase = useSupabaseClient();

const [classifications, setClassifications] = useState<any[]>([]);

const [loading, setLoading] = useState<boolean>(true);

const [error, setError] = useState<string | null>(null);

  

useEffect(() => {

const fetchClassifications = async () => {

setLoading(true);

setError(null);

try {

const { data, error } = await supabase

.from('classifications')

.select('id')

.filter('classificationConfiguration->activePlanet', 'eq', activePlanet);

  

if (error) throw error;

  

setClassifications(data);

} catch (error) {

console.error('Error fetching classifications:', error);

setError('Failed to load classifications.');

} finally {

setLoading(false);

}

};

  

fetchClassifications();

}, [activePlanet, supabase]);

  

if (loading) return <p>Loading...</p>;

if (error) return <p>{error}</p>;

if (classifications.length === 0) return <p>No classifications found for active planet {activePlanet}.</p>;

  

return (

<div className="flex flex-col space-y-4">

{classifications.map((classification) => (

<DiscoveryCardSingle key={classification.id} classificationId={classification.id} />

))}

</div>

);

}
```


# By Classification Type
```tsx
'use client';

  

import React, { useEffect, useState } from 'react';

import { useSession, useSupabaseClient } from '@supabase/auth-helpers-react';

import { DiscoveryCardSingle } from './Classification';

import { ChevronLeft, ChevronRight } from 'lucide-react';

  

interface DiscoveryCardsByClassificationTypeProps {

classificationtype: string;

};

  

export function DiscoveryCardsByClassificationType({ classificationtype }: DiscoveryCardsByClassificationTypeProps) {

const supabase = useSupabaseClient();

const session = useSession();

const [classifications, setClassifications] = useState<any[]>([]);

const [loading, setLoading] = useState<boolean>(true);

const [error, setError] = useState<string | null>(null);

const [currentIndex, setCurrentIndex] = useState(0);

  

useEffect(() => {

const fetchClassifications = async () => {

setLoading(true);

setError(null);

try {

const { data, error } = await supabase

.from('classifications')

.select('*')

.eq('classificationtype', classificationtype);

  

if (error) throw error;

  

setClassifications(data);

} catch (error) {

console.error('Error fetching classifications:', error);

setError('Failed to load classifications.');

} finally {

setLoading(false);

}

};

  

if (classificationtype) {

fetchClassifications();

}

}, [classificationtype, supabase]);

  

const goToNext = () => {

if (currentIndex < classifications.length - 1) {

setCurrentIndex(currentIndex + 1);

}

};

  

const goToPrev = () => {

if (currentIndex > 0) {

setCurrentIndex(currentIndex - 1);

}

};

  

if (loading) return <p>Loading...</p>;

if (error) return <p>{error}</p>;

if (classifications.length === 0) return <p>No classifications found for this classification type</p>;

  

return (

<div className="relative">

<div className="flex items-center space-x-4">

{/* Left Arrow Button */}

<button

onClick={goToPrev}

disabled={currentIndex === 0}

className="p-2 bg-gray-200 rounded-full disabled:opacity-50"

>

<ChevronLeft />

</button>

  

{/* Horizontal Scrolling Container */}

<div className="flex overflow-x-auto space-x-4 py-2">

{classifications.map((classification, index) => (

<div

key={classification.id}

className={`flex-shrink-0 ${index === currentIndex ? 'opacity-100' : 'opacity-50'}`}

>

<DiscoveryCardSingle key={classification.id} classificationId={classification.id} />

</div>

))}

</div>

  

{/* Right Arrow Button */}

<button

onClick={goToNext}

disabled={currentIndex === classifications.length - 1}

className="p-2 bg-gray-200 rounded-full disabled:opacity-50"

>

<ChevronRight />

</button>

</div>

</div>

);

};
```

# All Collections
```tsx
'use client';

  

import React, { useEffect, useState } from 'react';

import { useSession, useSupabaseClient } from '@supabase/auth-helpers-react';

import { DiscoveryCardSingle } from './Classification';

  

export function DiscoveryCards() {

const supabase = useSupabaseClient();

const session = useSession();

  

const [classifications, setClassifications] = useState<any[]>([]);

const [loading, setLoading] = useState<boolean>(true);

const [error, setError] = useState<string | null>(null);

  

useEffect(() => {

const fetchClassifications = async () => {

if (!session?.user) {

setError('User session not found.');

setLoading(false);

return;

};

  

setLoading(true);

setError(null);

try {

const { data, error } = await supabase

.from('classifications')

.select('*')

.eq('author', session.user.id);

  

if (error) throw error;

  

setClassifications(data);

} catch (error) {

console.error('Error fetching classifications:', error);

setError('Failed to load classifications.');

} finally {

setLoading(false);

};

};

  

fetchClassifications();

}, [session, supabase]);

  

if (loading) return <p>Loading...</p>;

if (error) return <p>{error}</p>;

if (classifications.length === 0) return <p>No classifications found for this user.</p>;

  

return (

<div className="flex flex-col space-y-4">

{classifications.map((classification) => (

<DiscoveryCardSingle key={classification.id} classificationId={classification.id} />

))}

</div>

);

};
```

