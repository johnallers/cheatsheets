**Extract PublicKey from snk for use with InternalsVisibleTo**

	REM Run the Visual Studio Command Prompt
	sn.exe -p SomeName.snk SomeName.PublicKey
	sn.exe -tp SomeName.PublicKey
