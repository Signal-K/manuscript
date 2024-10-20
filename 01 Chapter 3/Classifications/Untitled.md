---
sticker: lucide//arrow-big-right
tags:
  - Components
  - Classifications
---
Essentially, this is a component that serves as the feed, shows all your posts. I've removed this for now to save space but I do want to bring it back (or the overall format) once feeds, #Starnet and consensus makes their way into the gameplay loop

```tsx
import React, { useEffect, useState, useCallback } from "react";

import { useSession, useSupabaseClient } from "@supabase/auth-helpers-react";

import { format } from 'date-fns';

import ClassificationSummary from "../(anomalies)/(planets)/classificationsGenerated";

import { useActivePlanet } from "@/context/ActivePlanet";

import { Card, CardContent } from "@/components/ui/card";

import { Badge } from "@/components/ui/badge"

import { CalendarIcon, Users, Globe } from 'lucide-react'

  

interface Classification {

id: number;

content: string;

classificationtype: string;

anomaly: number | null;

created_at: string;

media: any[];

classificationConfiguration: Record<string, any>;

};

  

interface Anomaly {

id: number;

content: string;

};

  

interface ClassificationViewerProps {

classificationType: string;

};

  

const ClassificationViewer: React.FC<ClassificationViewerProps> = ({ classificationType }) => {

const supabase = useSupabaseClient();

const session = useSession();

  

const { activePlanet } = useActivePlanet();

  

const [classifications, setClassifications] = useState<Classification[]>([]);

const [anomalies, setAnomalies] = useState<Map<number, Anomaly>>(new Map());

const [selectedClassification, setSelectedClassification] = useState<Classification | null>(null);

const [offset, setOffset] = useState<number>(0);

const [loading, setLoading] = useState<boolean>(false);

const [showSummary, setShowSummary] = useState<boolean>(false);

  

const fetchClassifications = useCallback(async () => {

if (!classificationType || !session?.user?.id) return;

setLoading(true);

try {

const { data: classificationsData, error: classificationsError } = await supabase

.from('classifications')

.select('id, content, author, classificationtype, anomaly, created_at, media, classificationConfiguration')

.eq('author', session.user.id)

.eq('classificationtype', classificationType)

.range(offset, offset + 4);

if (classificationsError) throw classificationsError;

setClassifications(classificationsData as Classification[]);

const { data: anomaliesData, error: anomaliesError } = await supabase

.from('anomalies')

.select('id, content');

if (anomaliesError) throw anomaliesError;

const anomaliesMap = new Map<number, Anomaly>();

anomaliesData.forEach(anomaly => {

anomaliesMap.set(anomaly.id, anomaly);

});

setAnomalies(anomaliesMap);

} catch (error) {

console.error('Error fetching data:', error);

} finally {

setLoading(false);

};

}, [classificationType, offset, session?.user?.id, supabase]);

  

useEffect(() => {

fetchClassifications();

}, [fetchClassifications]);

  

const handleClassificationClick = (classification: Classification) => {

setSelectedClassification(classification);

};

  

const handleClose = () => {

setSelectedClassification(null);

};

const loadMore = () => {

setOffset(prevOffset => prevOffset + 5);

};

  

const formatDate = (dateString: string) => {

return format(new Date(dateString), 'MMMM d, yyyy');

};

  

return (

<div className="py-4 max-4-lg mx-auto text-white rounded-md">

<button

onClick={() => setShowSummary(prev => !prev)}

className="mb-4 px-4 py-2 bg-[#5FCBC3] text-white rounded-md"

>

{showSummary ? 'Show Classifications' : 'Show Summary'}

</button>

  

{showSummary ? (

<ClassificationSummary />

) : (

<>

{classificationType && (

<div className="p-0">

<h2 className="text-lg font-semibold mt-4">Classifications for {classificationType}: </h2>

<div className="mt-2 space-y-2">

{classifications.map((classification) => {

const anomalyContent = classification.anomaly ? anomalies.get(classification.anomaly)?.content : '';

return (

<DiscoveryCardComponent

key={classification.id}

name={classification.content}

type={classification.classificationtype}

profileImage={classification.media.length > 0 ? classification.media[1] : undefined}

discoveredOn={formatDate(classification.created_at)}

parentAnomaly={anomalyContent || "Earth"}

keyStats={[

{

label: 'Classification ID',

value: classification.id.toString()

},

{

label: 'Created At',

value: formatDate(classification.created_at)

},

]} collaborators={[]}

/>

);

})}

</div>

<button

className="mt-4 px-4 py-2 bg-[#5FCBC3] text-white rounded-md"

onClick={loadMore}

disabled={loading}

>

{loading ? 'Loading...' : 'Load More'}

</button>

</div>

)}

</>

)}

</div>

);

// return (

// <div className="p-4 max-w-lg mx-auto text-white rounded-md">

// <button

// className="mb-4 px-4 py-2 bg-[#5FCBC3] text-white rounded-md"

// onClick={() => setShowSummary(prev => !prev)}

// >

// {showSummary ? 'Show Classifications' : 'Show Summary'}

// </button>

  

// {showSummary ? (

// <ClassificationSummary />

// ) : (

// <>

// {classificationType && (

// <div>

// <h2 className="text-lg font-semibold mt-4">Classifications for {classificationType}:</h2>

// <div className="mt-2 space-y-2">

// {classifications.map((classification) => {

// const anomalyContent = classification.anomaly ? anomalies.get(classification.anomaly)?.content : '';

// return (

// <div

// key={classification.id}

// className="p-4 bg-[#2C3A4A] border border-gray-600 rounded-md flex flex-col cursor-pointer"

// onClick={() => handleClassificationClick(classification)}

// >

// <div className="flex items-start space-x-3">

// {anomalyContent && (

// <span className="text-yellow-300 font-semibold">{anomalyContent}</span>

// )}

// </div>

// <div className="mt-2">

// <p>{classification.content}</p>

// </div>

// <div className="mt-2 text-gray-400 text-sm">

// Posted on: {formatDate(classification.created_at)}

// </div>

// </div>

// );

// })}

// </div>

// <button

// className="mt-4 px-4 py-2 bg-[#5FCBC3] text-white rounded-md"

// onClick={loadMore}

// disabled={loading}

// >

// {loading ? 'Loading...' : 'Load More'}

// </button>

// </div>

// )}

  

// {selectedClassification && (

// <div className="fixed inset-0 bg-black bg-opacity-50 flex items-center justify-center">

// <div className="bg-[#2C3A4A] p-4 rounded-lg max-w-lg w-full overflow-y-auto">

// <h2 className="text-xl font-bold mb-4">Classification Details</h2>

// <div className="mb-4">

// <p className="text-lg font-semibold">{selectedClassification.content}</p>

// <div className="mt-2 text-gray-400 text-sm">

// Posted on: {formatDate(selectedClassification.created_at)}

// </div>

// </div>

// <div className="mb-4">

// {/* Media display */}

// <div>

// {selectedClassification.media && selectedClassification.media.length > 0 && (

// <div>

// {selectedClassification.media.map((item, index) => {

// const mediaUrl = typeof item === 'string' ? item : (Array.isArray(item) && typeof item[1] === 'string' ? item[1] : '');

// return mediaUrl ? (

// <div key={index} className="mb-2">

// <img

// src={mediaUrl}

// alt={`Media ${index}`}

// className="max-w-full h-auto"

// />

// </div>

// ) : (

// <div key={index} className="mb-2 text-red-500">

// </div>

// );

// })}

// </div>

// )}

// </div>

// </div>

// <div className="mb-4">

// {/* Classification Configuration */}

// <h3 className="text-lg font-semibold">Classification Configuration:</h3>

// <ul className="list-disc list-inside ml-4 text-gray-300">

// {Object.entries(selectedClassification.classificationConfiguration).map(([key, value]) => (

// <li key={key} className="mt-1">

// <strong>{key}:</strong> {value ? 'Yes' : 'No'}

// </li>

// ))}

// </ul>

// </div>

// <button

// className="px-4 py-2 bg-[#5FCBC3] text-white rounded-md"

// onClick={handleClose}

// >

// Close

// </button>

// </div>

// </div>

// )}

// </>

// )}

// </div>

// );

};

  

export default ClassificationViewer;

  

export const ClassificationViewerAll: React.FC = () => {

const supabase = useSupabaseClient();

const session = useSession();

  

const [classifications, setClassifications] = useState<Classification[]>([]);

const [anomalies, setAnomalies] = useState<Map<number, Anomaly>>(new Map());

const [selectedClassification, setSelectedClassification] = useState<Classification | null>(null);

const [offset, setOffset] = useState<number>(0);

const [loading, setLoading] = useState<boolean>(false);

const [showSummary, setShowSummary] = useState<boolean>(false);

  

const fetchClassifications = useCallback(async () => {

if (!session) {

return;

}

  

setLoading(true);

  

try {

// Fetch classifications

const { data: classificationsData, error: classificationsError } = await supabase

.from('classifications')

.select('id, content, author, classificationtype, anomaly, created_at, media, classificationConfiguration')

.eq('author', session?.user?.id)

.range(offset, offset + 4);

  

if (classificationsError) throw classificationsError;

  

setClassifications(classificationsData as Classification[]);

  

// Fetch anomalies

const { data: anomaliesData, error: anomaliesError } = await supabase

.from('anomalies')

.select('id, content');

  

if (anomaliesError) throw anomaliesError;

  

// Map anomalies for quick lookup

const anomaliesMap = new Map<number, Anomaly>();

anomaliesData.forEach(anomaly => {

anomaliesMap.set(anomaly.id, anomaly);

});

  

setAnomalies(anomaliesMap);

  

} catch (error) {

console.error('Error fetching data:', error);

} finally {

setLoading(false);

}

}, [offset, supabase]);

  

useEffect(() => {

fetchClassifications();

}, [fetchClassifications]);

  

const handleClassificationClick = (classification: Classification) => {

setSelectedClassification(classification);

};

  

const handleClose = () => {

setSelectedClassification(null);

};

  

const loadMore = () => {

setOffset(prevOffset => prevOffset + 5);

};

  

const formatDate = (dateString: string) => {

return format(new Date(dateString), 'MMMM d, yyyy');

};

  

return (

<div className="p-4 max-w-lg mx-auto text-white rounded-md">

<button

className="mb-4 px-4 py-2 bg-[#5FCBC3] text-white rounded-md"

onClick={() => setShowSummary(prev => !prev)}

>

{showSummary ? 'Show Classifications' : 'Show Summary'}

</button>

  

{showSummary ? (

<ClassificationSummary />

) : (

<>

<div>

<h2 className="text-lg font-semibold mt-4">Classifications:</h2>

<div className="mt-2 space-y-2">

{classifications.map((classification) => {

const anomalyContent = classification.anomaly ? anomalies.get(classification.anomaly)?.content : '';

return (

<div

key={classification.id}

className="p-4 bg-[#2C3A4A] border border-gray-600 rounded-md flex flex-col cursor-pointer"

onClick={() => handleClassificationClick(classification)}

>

<div className="flex items-start space-x-3">

{anomalyContent && (

<span className="text-yellow-300 font-semibold">{anomalyContent}</span>

)}

</div>

<div className="mt-2">

<p>{classification.content}</p>

</div>

<div className="mt-2 text-gray-400 text-sm">

Posted on: {formatDate(classification.created_at)}

</div>

</div>

);

})}

</div>

<button

className="mt-4 px-4 py-2 bg-[#5FCBC3] text-white rounded-md"

onClick={loadMore}

disabled={loading}

>

{loading ? 'Loading...' : 'Load More'}

</button>

</div>

  

{selectedClassification && (

<div className="fixed inset-0 bg-black bg-opacity-50 flex items-center justify-center">

<div className="bg-[#2C3A4A] p-4 rounded-lg max-w-lg w-full overflow-y-auto">

<h2 className="text-xl font-bold mb-4">Classification Details</h2>

<div className="mb-4">

<p className="text-lg font-semibold">{selectedClassification.content}</p>

<div className="mt-2 text-gray-400 text-sm">

Posted on: {formatDate(selectedClassification.created_at)}

</div>

</div>

<div className="mb-4">

{/* Media display */}

<div>

{selectedClassification.media && selectedClassification.media.length > 0 && (

<div>

{selectedClassification.media.map((item, index) => {

const mediaUrl = typeof item === 'string' ? item : (Array.isArray(item) && typeof item[1] === 'string' ? item[1] : '');

return mediaUrl ? (

<div key={index} className="mb-2">

<img

src={mediaUrl}

alt={`Media ${index}`}

className="max-w-full h-auto"

/>

</div>

) : (

<div key={index} className="mb-2 text-red-500">

</div>

);

})}

</div>

)}

</div>

</div>

<div className="mb-4">

{/* Classification Configuration */}

<h3 className="text-lg font-semibold">Classification Configuration:</h3>

<ul className="list-disc list-inside ml-4 text-gray-300">

{Object.entries(selectedClassification.classificationConfiguration).map(([key, value]) => (

<li key={key} className="mt-1">

<strong>{key}:</strong> {value ? 'Yes' : 'No'}

</li>

))}

</ul>

</div>

<button

className="px-4 py-2 bg-[#5FCBC3] text-white rounded-md"

onClick={handleClose}

>

Close

</button>

</div>

</div>

)}

</>

)}

</div>

);

};

  

interface Collaborator {

name: string

avatar: string

}

  

interface KeyStat {

label: string

value: string

}

  

interface DiscoveryCardProps {

name: string

type: string

profileImage?: string

discoveredOn: string

collaborators: Collaborator[]

parentAnomaly: string

keyStats: KeyStat[]

}

  

const generateImagePlaceholder = (name: string) => {

const canvas = document.createElement('canvas')

canvas.width = 200

canvas.height = 200

const context = canvas.getContext('2d')

if (context) {

context.fillStyle = `hsl(${Math.random() * 360}, 70%, 80%)`

context.fillRect(0, 0, canvas.width, canvas.height)

context.font = 'bold 80px Arial'

context.fillStyle = 'white'

context.textAlign = 'center'

context.textBaseline = 'middle'

context.fillText((name && name.length > 0) ? name.charAt(0).toUpperCase() : '?', canvas.width / 2, canvas.height / 2)

}

return canvas.toDataURL()

}

  

export function DiscoveryCardComponent({

name = 'Unnamed Discovery',

type = 'Unknown',

profileImage,

discoveredOn = 'Unknown',

collaborators = [],

parentAnomaly = 'Unknown',

keyStats = []

}: DiscoveryCardProps) {

const imageUrl = profileImage || generateImagePlaceholder(name)

  

return (

<Card className="w-full max-w-2xl bg-gradient-to-br from-slate-100 to-slate-200 text-slate-900 overflow-hidden relative border-2 border-slate-300 rounded-xl shadow-lg">

<CardContent className="p-6 flex">

<div className="w-1/3 pr-4 border-r border-slate-300">

<div className="aspect-square rounded-lg overflow-hidden mb-4 shadow-md">

<img src={imageUrl} alt={name} className="w-full h-full object-cover" />

</div>

<h2 className="text-2xl font-bold mb-2">{name}</h2>

<Badge variant="outline" className="bg-slate-800 text-white">

{type}

</Badge>

</div>

<div className="w-2/3 pl-4 flex flex-col justify-between">

<div className="space-y-4">

<div className="flex items-center space-x-2">

<CalendarIcon className="w-4 h-4 text-slate-600" />

<span className="text-sm">Discovered on: {discoveredOn}</span>

</div>

<div className="flex items-center space-x-2">

<Globe className="w-4 h-4 text-slate-600" />

<span className="text-sm">Parent Anomaly: {parentAnomaly}</span>

</div>

<div>

<div className="flex items-center space-x-2 mb-2">

<Users className="w-4 h-4 text-slate-600" />

<span className="text-sm font-semibold">Collaborators:</span>

</div>

<div className="flex flex-wrap gap-2">

{collaborators.length > 0 ? collaborators.map((collaborator, index) => (

<div key={index} className="flex items-center bg-slate-300 rounded-full px-2 py-1">

<img src={collaborator.avatar} alt={collaborator.name} className="w-6 h-6 rounded-full mr-2" />

<span className="text-xs">{collaborator.name}</span>

</div>

)) : (

<span className="text-sm text-slate-600">No collaborators</span>

)}

</div>

</div>

</div>

<div className="mt-4">

<h3 className="text-lg font-semibold mb-2">Key Stats</h3>

<div className="grid grid-cols-2 gap-2">

{keyStats.length > 0 ? keyStats.map((stat, index) => (

<div key={index} className="bg-slate-300 p-2 rounded-lg">

<p className="text-xs text-slate-600">{stat.label}</p>

<p className="text-sm font-semibold">{stat.value}</p>

</div>

)) : (

<div className="col-span-2 bg-slate-300 p-2 rounded-lg">

<p className="text-sm text-slate-600">No key stats available</p>

</div>

)}

</div>

</div>

</div>

</CardContent>

</Card>

)

}
```