# ipfs-stash
#
#  ___ ____  _____ ____    ____  _            _     
# |_ _|  _ \|  ___/ ___|  / ___|| |_ __ _ ___| |__  
#  | || |_) | |_  \___ \  \___ \| __/ _` / __| '_ \ 
#  | ||  __/|  _|  ___) |  ___) | || (_| \__ \ | | |
# |___|_|   |_|   |____/  |____/ \__\__,_|___/_| |_|
#

IPFS Stash is a small utility for adding files to a private IPFS Cluster. 

Stash initially perform an 'ipfs add' locally to obtain the CID before using 'ipfs-cluster-ctl' to instruct the private IPFS-Cluster to pin & replicate the CID.

It then replaces the original file with a small script, with the same name as the original file, which when executed performs an 'ipfs get' on the CID stored within it.


TODO:
 - opt to disable pinning in local IPFS cluster for archiving files that're no longere required locally
 - opt specify additional tags for database
 - parameterise pin replicas
 - opt to not replace original file for files that're still needed locally
 - restore preflight sanity checks for local ipfs environment, file type, available disk space in local ipfs repo