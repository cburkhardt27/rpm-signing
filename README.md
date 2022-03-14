# rpm-signing

Import Public Key:
	`rpm --import GGP-KEY-NBAME`
	
Check Imported Public Keys:
	`rpm -q gpg-pubkey --qf '%{name}-%{version}-%{release} --> %{summary}\n'`
	
Verify Signatures
	`rpm -KV <rpm-pkg-name>`
	`rpm --checksig -v <rpm-pkg-name>`
	
Sign
	Import public key of your GPG key into the RPM database
	
	Add to .rpmmacros:
	```
	%_signature gpg
	%_gpg_path ~/.gnupg
	%_gpg_name <Key Name> 
	%_gpgbin /usr/bin/gpg
	```
	`rpm --addsign <rpm-pkg-name>`
