PHASE ONE

Guest Book
==========

[![Build Status](https://travis-ci.com/near-examples/guest-book.svg?branch=master)](https://travis-ci.com/near-examples/guest-book)

[![Open in Gitpod](https://gitpod.io/button/open-in-gitpod.svg)](https://gitpod.io/#https://github.com/near-examples/guest-book)

<!-- MAGIC COMMENT: DO NOT DELETE! Everything above this line is hidden on NEAR Examples page -->

Sign in with [NEAR] and add a message to the guest book! A starter app built with an [AssemblyScript] backend and a [React] frontend.


Quick Start
===========

To run this project locally:

1. Prerequisites: Make sure you have Node.js ≥ 12 installed (https://nodejs.org), then use it to install [yarn]: `npm install --global yarn` (or just `npm i -g yarn`)
2. Run the local development server: `yarn && yarn dev` (see `package.json` for a
   full list of `scripts` you can run with `yarn`)

Now you'll have a local development environment backed by the NEAR TestNet! Running `yarn dev` will tell you the URL you can visit in your browser to see the app.


Exploring The Code
==================

1. The backend code lives in the `/assembly` folder. This code gets deployed to
   the NEAR blockchain when you run `yarn deploy:contract`. This sort of
   code-that-runs-on-a-blockchain is called a "smart contract" – [learn more
   about NEAR smart contracts][smart contract docs].
2. The frontend code lives in the `/src` folder.
   [/src/index.html](/src/index.html) is a great place to start exploring. Note
   that it loads in `/src/index.js`, where you can learn how the frontend
   connects to the NEAR blockchain.
3. Tests: there are different kinds of tests for the frontend and backend. The
   backend code gets tested with the [asp] command for running the backend
   AssemblyScript tests, and [jest] for running frontend tests. You can run
   both of these at once with `yarn test`.

Both contract and client-side code will auto-reload as you change source files.


Deploy
======

Every smart contract in NEAR has its [own associated account][NEAR accounts]. When you run `yarn dev`, your smart contracts get deployed to the live NEAR TestNet with a throwaway account. When you're ready to make it permanent, here's how.


Step 0: Install near-cli
--------------------------

You need near-cli installed globally. Here's how:

    npm install --global near-cli

This will give you the `near` [CLI] tool. Ensure that it's installed with:

    near --version


Step 1: Create an account for the contract
------------------------------------------

Visit [NEAR Wallet] and make a new account. You'll be deploying these smart contracts to this new account.

Now authorize NEAR CLI for this new account, and follow the instructions it gives you:

    near login


Step 2: set contract name in code
---------------------------------

Modify the line in `src/config.js` that sets the account name of the contract. Set it to the account id you used above.

    const CONTRACT_NAME = process.env.CONTRACT_NAME || 'your-account-here!'


Step 3: change remote URL if you cloned this repo 
-------------------------

Unless you forked this repository you will need to change the remote URL to a repo that you have commit access to. This will allow auto deployment to GitHub Pages from the command line.

1) go to GitHub and create a new repository for this project
2) open your terminal and in the root of this project enter the following:

    $ `git remote set-url origin https://github.com/YOUR_USERNAME/YOUR_REPOSITORY.git`


Step 4: deploy!
---------------

One command:

    yarn deploy

As you can see in `package.json`, this does two things:

1. builds & deploys smart contracts to NEAR TestNet
2. builds & deploys frontend code to GitHub using [gh-pages]. This will only work if the project already has a repository set up on GitHub. Feel free to modify the `deploy` script in `package.json` to deploy elsewhere.



  [NEAR]: https://near.org/
  [yarn]: https://yarnpkg.com/
  [AssemblyScript]: https://www.assemblyscript.org/introduction.html
  [React]: https://reactjs.org
  [smart contract docs]: https://docs.near.org/docs/develop/contracts/overview
  [asp]: https://www.npmjs.com/package/@as-pect/cli
  [jest]: https://jestjs.io/
  [NEAR accounts]: https://docs.near.org/docs/concepts/account
  [NEAR Wallet]: https://wallet.near.org
  [near-cli]: https://github.com/near/near-cli
  [CLI]: https://www.w3schools.com/whatis/whatis_cli.asp
  [create-near-app]: https://github.com/near/create-near-app
  [gh-pages]: https://github.com/tschaub/gh-pages
  
  
  
  PHASE TWO
  
  JMA_DAO Wallet
  ==============
  
  Add wallet integrstions after message description, to allow for payment with any listed cryptocurency of choice. 
  
  JMA_DAO Wallet will have three major smart contrct interactions.
  1. Make payment with any listed cryptocurency of choice, with a message description. (visble to all CM on wallet interface)
  2. Smart Contract Automatically swaps all payment to JMA_DAO native stable cryptocurency (visible on cahin, using forked Explore)
  3. PayOut with JMA_DAO native currency, a smart contract response to message description from 1. above. (visible to all CM on wallet interface)

Payment System Description!
The JMA_DAO community uses a native satble cryptocurrency for all its pay outs. Payment made by the community members has a description that details the purpose of the paynent. When paymenyt is made (using any listed Cryptocurency) 
it goes to the JMA_DOA Escrow acount in the wallet (not visible on the wallet but availble on chain) the Escrow account automatically swaps all incominmg payment to the JMA_DAO native stable coin using a hybrid smart contract. 
Payouts are then made to curresponding account using the information in the message description. All payouts are make using the JMA_DAO native stable cryptocurrency.![JMA_DOA Wallet System (1)](https://user-images.githubusercontent.com/81659794/204951712-d7122d31-80a9-440a-b7e4-10f9fabbc41a.png)


  
  
  
  
  
