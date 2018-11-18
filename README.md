# LerGO Codeship Build

> A build for LerGO running on Codeship

# Running with Jet client

 - Install codeship's jet cli.
 - Run command `jet load --ci-build-id=local-build lergo-build`
 - Run command `jet steps --ci-build-id=local-build build-lergo` to run the build step.

# Encrypting / Decrypting environment variables

 - Download AES file from codeship project settings -- general.
 - `jet decrypt env.encrypted env.decrypted`
 - `jet encrypt env.decrypted env.encrypted`


# Encrypting other files

Currently still using openssl until I'll figure out how to use jet-cli if possible.   
https://stackoverflow.com/questions/53357612/how-should-i-use-codeship-encrypted-files-in-ci

TESTME_KEY can be found using jet-cli to decrypt env.encrypted (see commands above)

 - `openssl aes-256-cbc -a -salt -in dev/testMe.json -out scripts/testMe.json.enc -pass  pass:$TESTME_KEY`
