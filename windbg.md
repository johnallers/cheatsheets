**Identify .NET version**

	lm v m mscorwks
	lm v m clr

**Automatically load mscordacwks**

	.cordll -ve -u -l


**Load mscordacwks from a specific location**

    .cordll -ve -u -lp C:\mylocalsymcache

**Load SOS for .NET 4.0**

    .loadby sos clr

**Load PSSCOR from a specific location**

    .load C:\Temp\Psscor4\amd64\psscor4.dll

**Misc**

	!threads
