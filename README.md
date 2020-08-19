## SkyFile

SkyFile is a command line utility to upload and get files from Sia Skynet.
It also allows you to assign a Handshake domain name to an uploaded file. 
You can then fetch the file from Sia Skynet using the Handshake domain name.

## Demo Video
https://www.youtube.com/watch?v=rdlz3DugcdY

## Getting Started

1. Clone Skyfile repo

   ```
   git clone https://github.com/viraja1/skyfile.git
   cd skyfile
   ```
   
2. Upload the file to Skynet

   ```
   ./skyfile upload {file_path} 
   ```   
   e.g. ./skyfile upload /tmp/skynet.txt
   
   Note down the generated skylink since it will be required to fetch 
   the file from Skynet 
      
3. Upload the file to Skynet and assign a custom Handshake domain

   Create an account at https://www.namebase.io and purchase a custom 
   Handshake TLD. Then generate an API key at https://www.namebase.io/pro/keys
   
   Then export the namebase credentials and TLD name as an environment 
   variable.
   
   ````
   export NAMEBASE_API_KEY=
   export NAMEBASE_SECRET_KEY=
   export NAMEBASE_TLD=
   ````
   
   Then upload the file to Skynet using the following command
   
   ```
   ./skyfile upload {file_path} {custom_name}
   ```
   e.g. ./skyfile upload /tmp/skynet.txt skynet
   
   If  NAMEBASE_TLD=nettie and custom name is skynet, then the skylink
   will be assigned a domain named skynet.nettie
   
4. Fetch the file from Skynet using skylink
   
   ```
   ./skyfile get {skylink} 
   ```
   
   e.g. ./skyfile get AACxjWhnQOLUumaMuOIfue1kcOLThg4TMYVXDgaO67tKiw

5. Fetch the file from Skynet using a Handshake domain name

   ```
   ./skyfile get {handshake_domain_name} 
   ```
   
   e.g. ./skyfile get skynet.nettie
