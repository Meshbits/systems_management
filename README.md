# systems_management
Temporary spot for this info


## Maintaining https://github.com/Meshbits/komodo for now

To minimise the impact of any unforeseen changes with upstream[s] on the work being done by Meshbits, we're trying to maintain a fork. **I acknowledge that it's not the best strategy but we're doing it for now.**

Currently KomodoPlatform features are being developed in a fairly decentral way which is good. But one of the side-effects have been that features are a bit all over the place.
- https://github.com/KomodoPlatform/komodo:master - **is supposed to** contain stable features and used by notary nodes.
- https://github.com/jl777/komodo:dev - dexp2p and subatomic features are only present in this repo.

We initially tried automating it but because of the conflicts between changes being introduced by both upstream, we're using the manual approach.

```shell

git clone git@github.com:Meshbits/komodo.git
cd komodo

git remote add jl777 git@github.com:jl777/komodo.git
git remote add komodoplatform git@github.com:KomodoPlatform/komodo.git

# Merge changes from jl777
git fetch jl777 dev
git merge jl777/dev

# Merge changes from komodoplatform
git fetch komodoplatform dev
git merge komodoplatform/dev

# Scenario: During merge conflict, grab FILENAME[s] from a different origin
git checkout komodoplatform/dev FILENAME[s]
```
