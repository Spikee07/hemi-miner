# hemi-miner

## VPS guide for Setting Up Hemi-Miner

Welcome to the Hemi-Miner setup guide! Follow these steps to get Hemi-Miner up and running on your vps.

### Download and Setup

1. **Download the Hemi Network Binary**
   ```bash
   wget https://github.com/hemilabs/heminetwork/releases/download/v0.5.0/heminetwork_v0.5.0_linux_amd64.tar.gz
   ```

2. **Create a Directory for Hemi**
   ```bash
   mkdir hemi
   ```

3. **Extract the Downloaded Archive**
   ```bash
   tar --strip-components=1 -xzvf heminetwork_v0.5.0_linux_amd64.tar.gz -C hemi
   ```

4. **Navigate to the Hemi Directory**
   ```bash
   cd hemi
   ```

### Configuration

5. **Generate Wallet (MUST DO)**
   ```bash
   ./keygen -secp256k1 -json -net="testnet" > popm-address.json
   ```
   IF YOU HAVE OLD WALLET YOU MUST DO GENERATE WALLET AND THEN IMPORT YOUR OLD PRIVATE KEY IN NUMBER 8

6. **SEE WALLET**
   ```bash
   cat popm-address.json
   ```

7. **Set Up Environment Variables (MUST DO) YOU CAN USE OLD PRIVATE KEY OR NEW (SEE USE NO 8)**
   
   Replace `your pk` with your private key.
   ```bash
   export POPM_BTC_PRIVKEY=your pk
   export POPM_STATIC_FEE=400
   export POPM_BFG_URL=wss://testnet.rpc.hemi.network/v1/ws/public
   ```

### Run the Miner

**USE SCREEN**
   ```bash
   screen -S hemi
   ```

8. **Start the Hemi Miner**
   ```bash
   ./popmd
   ```
   
**CLOSE SCREEN**
   ```bash
   ctrl a + d 
   ```
**OPEN SCREEN**
   ```bash
   screen -r hemi
   ```

Happy Mining ⛏️ 
