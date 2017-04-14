View certificates in the machine's Personal store:

    certutil -store my

View certificates in the user's Personal store:

    certutil -user -store my

Import certificate and private key using a specific CSP:

    certutil -CSP "Microsoft Software Key Storage Provider" -ImportPFX idp.pfx
