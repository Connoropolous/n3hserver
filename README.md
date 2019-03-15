# n3hserver

[![Deploy](https://www.herokucdn.com/deploy/button.svg)](https://heroku.com/deploy)

This uses [this branch](https://github.com/holochain/n3h/compare/heroku-test) of n3h to create a simple n3h server

Note that https was removed at the level it was being handled before, because heroku handles wss a different way.

Once you start it run, run `heroku logs` from a CLI or look at the logs in the web app dashboard

Grab one of the last lines into your clipboard, that looks like this:
`wss://172.19.41.82:47423/?a=hkYcCLPsTGt_O4hxyQRC1tCdjxI7PbSSPbQ7mAE1cpTuAdvQLmNdqJuB0gjhdijiLpSXkwvrqSijMknrDev0q_UvCSELUDGM`
right after "#P2P-BINDING#:"

Edit the IP address and port so that it's instead the URL of the app, e.g. 
`wss://n3hserver.herokuapp.com/...`

Paste that URL into a `wssRelayPeers` array for a network config JSON for n3h to connect to it.
