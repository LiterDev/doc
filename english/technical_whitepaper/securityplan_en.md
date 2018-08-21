## Office Security	
  - Block external hacking attempts and malicious access to the office network
    - Network Security	
      - Disable Wifi
	  - Disable unnecessary network usage
	  - Separate intranet and external network (Intranet disables the access from the external network.)
  	- PC Security	 
  	  - Prohibit usage of windows os
	  - Physically locks Principal PC
	- Document Security	
	  - Encrypt important document
	  - Prohibit unauthorized USB
	  - Apply e-mail management solution (prohibit undiscerning sending e-mail to external address)
	- Security Training	
	  - Using security breaching case studies, security training takes place regularly

## Wallet Security	
  - ICO Wallet Management	
    - Private key
      - Store with hard wallet
	- Private key multi sig	
	  - since erc-20 does not support multi-sig, separates private key in 3by2 form, and founders hold each keys.
  - LITER EOS Wallet Management	
    - Hot wallet	
      - 5% of the total issued cryptocurrency 
	- Cold wallet	
	  - Store with hard wallet
	- Cold wallet multi sig	
	  - EOS based multi sig 
	  - develop 3by2 withdrawal feature
	  - two founders hold each keys.

## Security Infrastructure
  - LITER platform server security	
    - VPC	
      - Using VPC of AWS, separates networks
	- Install VPN
	  - Limit accessible pc and using open vpn, allows approved pc to access to the server\
  - Separate Blockchain Server	
    - Limited access to blockchain node server	
      - Blockchain node server can be accessed only by approved ip.
  - Limited DB Access	
    - External client cannot acces to operating DB.	
      - Accessible ip to DB is limited to liter application.

## Privacy Policy	
  - LITER service user data security	
    - Limit collecting sensitive personal data	
      - Identification Number(such like SSN), bank account number etc
  - Personalizing user data security	
    - Personalizing data which analyzes user behavior will be used and exposed upon user's approval. 
  - Physical Security	
    - Encrypt DB and personalized data recorded on the blockchain using ECC.
    - Select irreversible data and record on the blockchain.
