# 🏛️ FHE Vault

## On-Chain decentralized vault proteced by FHE based Multi Factor

**Deployed Links**
[FHE Vault](https://fhe-vault-client.vercel.app/)
[FHE Authenticator](https://fluf-id.vercel.app/id)

**Table of Contents**

- Description
- Installation
- UX Flow and Screenshots
- Architecture Flow
- Use of fhEVM
- Future Goals

## Description

**Secure Multi-Factor Authentication (MFA) for Decentralized Vaults**

FHE Vault offers a robust Multi-Factor Authentication (MFA) solution, integrated with decentralized vaults for enhanced security. Users can sign up with their wallet on Zama Testnet or any supported FHEVM, setting up a passcode to access their MFA page. Once unlocked, users can seamlessly add their decentralized applications (DApps) for Two-Factor Authentication (2FA). The Fluf Authenticator generates unique 2FA codes using Fully Homomorphic Encryption (FHE) cryptography, ensuring unparalleled protection for accessing private vaults. This README provides an overview of the setup process and usage instructions for FHE Vault.

## Installation

Using git submodules we need to fetch the different components for this project. We can clone the repository then fetch the submodules.

```
git clone https://github.com/BruhmaHQ/fhe-vault.git
cd fhe-vault
git submodule update --init --recursive
```

**Server Setup**
Use the .example.env to setup your local enviornment

```
cd fluf-id-backend
npm i
npm start
```

**Client Setup**

` cd fluf-id-client` or ` cd fluf-vault-client`

```
npm i
npm run dev
```

## UX Flow

1.  **Sign Up with Fluf-ID Client:**

    - User visits the Fluf-ID Client interface.
    - They initiate the sign-up process by connecting their wallet to the Zama Testnet (or any supported FHEVM).
    - During sign-up, the user sets up a passcode which will act as a gate for accessing their MFA page.

2.  **MFA Page Setup:**

    - After successful sign-up, the user gains access to their MFA page.
    - They unlock the MFA page using the passcode they set up earlier.
    - Once unlocked, they proceed to set up Two-Factor Authentication (2FA) for additional security.

3.  **Adding DApp for 2FA:**

    - Within the MFA page, the user has the option to add their DApp (Decentralized Application) for Two-Factor Authentication.
    - They select the option to add a new DApp.
    - The user inputs the necessary information or scans a QR code provided by the DApp to register it with the Fluf Authenticator.

4.  **Generating 2FA Code:**

    - Upon successful registration of the DApp, the user is now ready to use 2FA for accessing their private vault.
    - Whenever they want to login to access their vault, they navigate to the FHE Vault login page.
    - They input their credentials (e.g., username and password).
    - The login process prompts them for 2FA.
    - The Fluf Authenticator generates a unique 2FA code using FHE cryptography for the specific DApp associated with the vault.

5.  **Authentication and Access:**

    - The user inputs the 2FA code generated by the Fluf Authenticator using FHE.
    - Upon successful authentication, the user gains access to their private vault.
    - They can now securely view and manage their encrypted data stored within the vault.

### Authenticator

![ID Creation](/demo/id-create.png)
![pin](/demo/id-otp.png)
![daap otp](/demo/id-verify.png)

### FHE Vault

![signup](/demo/login.png)
![login](/demo/signup.png)

## Architecture

Tech Stack : NextJS, TypeScript, NodeJS, Solidity, TailwindCSS

## Future Goals

Our goal is to create an Mobile or Progressive Web App (PWA) for the On-Chain Authenticator, providing users with seamless access to their authentication keys stored securely on the blockchain. Additionally, we aim to create a SDK, enabling decentralized applications to integrate on-chain Two-Factor Authentication (2FA) effortlessly.
