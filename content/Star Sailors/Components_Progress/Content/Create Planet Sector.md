---
title: CreatePlanetSector.tsx
tags:
  - Star-Sailors
  - Sector
  - Empty
---

Path: `components/Content/Planets/CreatePlanetSector.tsx`

```tsx
import React, { useEffect, useState } from "react";

import { useSupabaseClient, useSession } from "@supabase/auth-helpers-react";

  

function CreatePlanetSectorComponent ({ planetId }) {

const supabase = useSupabaseClient();

const session = useSession();

const [isLoading, setIsLoading] = useState(false);

  

const createSector = () => {

if (!session) { return; };

  

if (!planetId) { return; };

  

// Generate random mineral deposits - will later be set in db

const depsitCount = Math.floor(Math.random() * 5);

};

};
```

I think this might be a component/script that was unfinished? Must look into this

Update -> appears `components/Content/Planets/IndividualPlanet.tsx` is also another component. Might be from the v1 (`CPW-8` branch) template
	Update 2 -> actually another way of showing the planet content in dynamic routing/pages. So should keep that here for now