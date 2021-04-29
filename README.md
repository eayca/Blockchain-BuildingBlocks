# Blockchain-BuildingBlocks

1. Create account for each nodes
    - ./geth --datadir node1 account new

    - ./geth --datadir node2 account new

2. Generate the genesis block

    - Run puppeth:
    ![puppeth]()

    - For Which accounts are allowed to seal? : paste both nodes addresses

    - For Which accounts should be pre-funded? section : paste both nodes addresses

    - To Specify your chain/network ID : give 3 digit ID number

    - For What would you like to do? : select Manage existing genesis and then Export genesis configurations

    - Save the json file.

3. Initialize the nodes

    - ./geth --datadir node1 init testnetwork.json

    - ./geth --datadir node2 init testnetwork.json

4. Mining blocks
    - In seperate terminal, run the nodes: (need to enter the password of the nodes right after running the code)

        - ./geth --datadir node1 --unlock "NODE ONE ADDRESS" --mine --rpc --allow-insecure-unlock

        - ./geth --datadir node2 --unlock "NODE TWO ADDRESS" --mine --port 30304 --bootnodes "NODE ONE ENODE ADDRESS ENDING WITH :30303" --ipcdisable --allow-insecure-unlock

5. MyCrypto - setting the custom network

    - Select Change Network

    - Select Add Custom Node
    ![customnode]()


6. MyCrypto - Transaction

    - On View and Send, choose Keystore File

    - Select Node1 keystore file

    - After accessing your wallet, make a transaction to your Node2 address
    ![nodeone]()

    - TX Status
    ![txstatus]()

    - Transaction - Pending
    ![pending]()

        - May need to stop Node1 and Node2 command and restart it to transaction to be successful. 
    - Transaction - Successful
    ![successful]()


