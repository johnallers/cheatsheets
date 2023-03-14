View certificates in the machine's Personal store:

    certutil -store my

View certificates in the user's Personal store:

    certutil -user -store my

Import certificate and private key using a specific CSP:

    certutil -CSP "Microsoft Software Key Storage Provider" -ImportPFX idp.pfx

List All CSPs

	certutil -csplist

More: http://planetmediocrity.com/2013/10/certutil-exe-undocumented-switches/

CSP Test (List supported algorithms)

	 certutil -csptest -csp "Microsoft Software Key Storage Provider"
