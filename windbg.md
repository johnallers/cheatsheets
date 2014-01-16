**Identify .NET version**

	lm v m mscorwks
	lm v m clr

**Identify architecture**

	vertarget 

**Load PSSCOR from a specific location**

    .load C:\Temp\Psscor4\amd64\psscor4.dll

**Run Exception Analysis**

	!analyze -ve

**Misc**

	!threads


----------

**Automatically load mscordacwks**

	.cordll -ve -u -l


**Load mscordacwks from a specific location**

    .cordll -ve -u -lp C:\mylocalsymcache

**Load SOS for .NET 4.0 (Must match mscordacwks, but may not be necessary to load.  Psscor loads a subset of SOS)**

    .loadby sos clr