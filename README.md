# ipfs_utils.py

### A script with basic functionality for IPFS

AKA How to use [Blockfrost.io](https://blockfrost.io) to upload and pin images in the IPFS world

Note: You will need a Blockfrost.io account and IPFS project key to work with this code.

## Commands:

### Upload image to Blockfrost.io:

![deafmice_logo_500x500_blk_wht.png](deafmice_logo_500x500_blk_wht.png)

```bash
python ipfs_utils.py --create_ipfs deafmice_logo_500x500_blk_wht.png

# Returns the following to the terminal:

python ipfs_utils.py --create_ipfs deafmice_logo_500x500_blk_wht.png
deafmice_logo_500x500_blk_wht.png
Uploaded image to Blockfrost
{'name': 'deafmice_logo_500x500_blk_wht.png', 'ipfs_hash': 'QmdFSaManZiMHqYWj8K48WpFbZ1HGwv9LJdLacC6S5SQES', 'size': '43437'}
Created IPFS Hash
FIN
```

### Pin It:

```bash
python ipfs_utils.py --pin_ipfs QmdFSaManZiMHqYWj8K48WpFbZ1HGwv9LJdLacC6S5SQES

# Returns the following to the terminal:

QmdFSaManZiMHqYWj8K48WpFbZ1HGwv9LJdLacC6S5SQES
Pinned on Blockfrost
{'ipfs_hash': 'QmdFSaManZiMHqYWj8K48WpFbZ1HGwv9LJdLacC6S5SQES', 'state': 'queued'}
Pin IPFS Hash
FIN

```

### Verify Image is accessible from other gateways:

```bash
python ipfs_utils.py --check_ipfs QmdFSaManZiMHqYWj8K48WpFbZ1HGwv9LJdLacC6S5SQES

# Returns the following to the terminal:

QmdFSaManZiMHqYWj8K48WpFbZ1HGwv9LJdLacC6S5SQES
200
200
Availability:  [True, True]
Check IPFS Hash
FIN

```

### Remove the pin:

```bash
python ipfs_utils.py --remove_ipfs QmdFSaManZiMHqYWj8K48WpFbZ1HGwv9LJdLacC6S5SQES

# Returns the following to the terminal:

QmdFSaManZiMHqYWj8K48WpFbZ1HGwv9LJdLacC6S5SQES
Removing pin worked
{'ipfs_hash': 'QmdFSaManZiMHqYWj8K48WpFbZ1HGwv9LJdLacC6S5SQES', 'state': 'unpinned'}
Remove IPFS Hash
FIN

```


## Pre-setup

Clone the repo

```bash
git clone https://gitlab.com/deafmice/ipfs_utils.git
```

You need a local `.env` file [see the example below]

```bash
source .env
```

Create a virtualenv, then source it, then pip install the requirements [requests module mainly]

```bash
virtualenv -p python3 venv
source venv/bin/activate
pip install -r requirements.txt
```


### EXAMPLE local .env file

```bash
# Blockfrost API
export BLOCKFROST_IPFS=YOUR_API_KEY
```

