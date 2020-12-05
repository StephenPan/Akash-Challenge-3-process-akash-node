# Akash-Challenge-3-process-akash-node
Akash Challenge 3 process -Deployed akash node             

+ https://github.com/StephenPan/The-Akashian-Challenge +

Note that this akash single node is deployed on akash decloud, which is different from the VPS that needs to be deployed in the second week.

The process is the same as before. I have sorted out the instructions and notes, and the instructions will be clearer. What you need can be copied and used directly. VSCode can be directly edited by connecting to the server through the remote-ssh plug-in, which is more convenient than using vim. Or like I use Mac local wallet.




----------------------------------------------------------------------------------------------------------------------------------

#! /bin/bash
AKASH_NET="https://raw.githubusercontent.com/ovrclk/net/master/edgenet"
AKASH_NODE="tcp://rpc-edgenet.akashdev.net:26657"
AKASH_CHAIN_ID="akash-edgenet-1"
ACCOUNT_ADDRESS="Fill in your own."
KEY_NAME="Fill in your own"
KEYRING_BACKEND="os"
PROVIDER=Fill in your own
DSEQ=fill in your own
GSEQ=1
OSEQ=1
CODE=Fill in your own

# 1. initiate the deployment transaction, taking care to change the yml file
# akash tx deployment create deploy1-3.yml --from $KEY_NAME --node $AKASH_NODE --chain-id $AKASH_CHAIN_ID -y

# 2. query the list of deployed mirrors, need to wait a while, and modify the variables above after exporting the PROVIDER and DSEQ.
# akash query market lease list --owner $ACCOUNT_ADDRESS --node $AKASH_NODE --state active

# 3. upload the deployment license, no output, and change the yml file.
# akash provider send-manifest deploy1-3.yml --node $AKASH_NODE --dseq $DSEQ \\\
# --oseq $OSEQ --gseq $GSEQ --owner $ACCOUNT_ADDRESS --provider $PROVIDER

# Query the status of a single deployment license to get the web address of the service.
# akash provider lease-status --node $AKASH_NODE --dseq $DSEQ --oseq $OSEQ \\\
# --gseq $GSEQ --provider $PROVIDER --owner $ACCOUNT_ADDRESS

# Get the json to submit.
# akash query market lease get --dseq $DSEQ --gseq $GSEQ --oseq $OSEQ \\\\
# --provider $PROVIDER --owner $ACCOUNT_ADDRESS --node $AKASH_NODE -o json > $CODE.json

# Check your account balance
#akash query bank balances --node $AKASH_NODE $ACCOUNT_ADDRESS

# Cancel Deployment
#akash tx deployment close --node $AKASH_NODE --chain-id $AKASH_CHAIN_ID \ \ \ \ \ \
# --dseq $DSEQ --owner $ACCOUNT_ADDRESS --from $KEY_NAME -y

Translated with www.DeepL.com/Translator (free version)

---------------------------------------------------------------------------------------------------------------------------------------


The DSL file can be obtained from the ovrclk/docs library on GitHub https://github.com/ovrclk/docs/blob/master/testnet-challenges/deploy-1-3.yaml

After the deployment is completed, it is an akash node. 

！！！！Remember that commit at 1:00 in the morning is calculated based on the timestamp of the commit, the faster the reward, the higher the reward!!!!


https://akash-web-prod.s3.amazonaws.com/uploads/2020/12/Screen-Shot-2020-12-01-at-1.01.39-PM-1024x408.png


For more information about Akash, please use the following links to learn more.

Official Website: https://akash.network/?lang=zh-hans

Twitter: https://twitter.com/akashnet_

Telegram: https://t.me/AkashNW
