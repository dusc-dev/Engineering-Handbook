# Welcome to DUSC

- [ ] Gmail
- [ ] Slack DUSC
    Add as Member
- [ ] Slack Clients
	Add as External
- [ ] Everhour
    Add as Member
    Explaining Billing Practices
        - Add existing time
        - Install the timer extension
        - Start the timer
            - Equivalent to being in the office
            - Include bathroom/coffee getting
            - Does not include, chores/lunch/etc
            - Prefer to use timer rather than backfill
        - Stop the timer
- [ ] Xero
    Use Personal email
    Invite to Xero Me
    Home Address
    Emergency Contact
    Tax File Number
    Bank account
    Superannuation provider
    Superannuation member details
    Payment Items
        Ordinary Hours
        Superannuation Standard Rate
    Leave Items
        Annual Leave FTE x 20 x 7
        Personal/Carer Leave FTE x 10 x 7
- [ ] Github
    Invite to DUSC Team
    Invite to Client Teams
    [User add @dusc.dev email to profile](https://github.com/settings/emails)
    [Route Client to dusc.dev](https://github.com/settings/notifications/custom_routing)
- [ ] Password Manager
    Invite to Client Teams
    Add to Engineering Vault
- [ ] Datadog
    Invite to Client Teams
- [ ] Honeybadger
    Invite to Client Teams
- [ ] Heroku
    Invite to Client Teams
- [ ] Orbstack
    Add additional license
    Add to DUSC Team
- [ ] Airfocus
    Client must invite

# Developer

- [ ] Install
    `xcode-select --install`
- [ ] [Install Homebrew](https://brew.sh/)
- [ ] [Install 1Password](https://1password.com/downloads/mac/)
- [ ] Install Git
    `brew install git`
- [ ] Install Github CLI
    `brew install gh`
- [ ] Install mkcert
    `brew install mkcert`
- [ ] Login to Github
    `gh auth login` -> https
- [ ] Install Heroku CLI
    `brew tap heroku/brew && brew install heroku`
- [ ] Login to Heroku
    `heroku login`
- [ ] Sign up to Orbstack with @dusc.dev email
- [ ] [Install Orbstack (instead of Docker)](https://orbstack.dev/)
    Onboarding Questions:
        Choose Docker
        Settings -> System
            Memory 16Gb
            CPU None
- [ ] [Authenticate with the Container Registry](https://docs.github.com/en/packages/working-with-a-github-packages-registry/working-with-the-container-registry#authenticating-to-the-container-registry)
    [Create Personal Access Token to Read Packages](https://github.com/settings/tokens/new)
    `export CR_PAT=YOUR_TOKEN && echo $CR_PAT | docker login ghcr.io -u USERNAME --password-stdin`
- [ ] [Install VsCode](https://code.visualstudio.com/)
- [ ] [Install 1Password](https://1password.com/downloads/mac/)
- [ ] [Generate SSH Key](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent)
    `ssh-keygen -t ed25519 -C "you@dusc.dev"`
- [ ] [Add your SSH Key to your Github Profile](https://github.com/settings/keys)
- [ ] Share your public key with onboarder
    `cat ~/.ssh/id_ed25519.pub | pbcopy`
- [ ] Onboarder to add Key to required projects

# Application

- [ ] Discuss replacement `{CLIENT}` and `{REPO}` values with onboarder
- [ ] Create `~/src/{CLIENT}` directory `mkdir -p ~/src/{CLIENT}`
- [ ] Clone Repositories into `~/src/{CLIENT}/{REPO}`
    `git clone https://github.com/{CLIENT}/{REPO}.git`
- [ ] On host machine install certificates
    `CAROOT=~/src/{CLIENT}/{REPORT}/nginx/certs/ mkcert -install`
- [ ] Open VSCode, open
    `~/src/{CLIENT}/{REPO}/{REPO}.code-workspace`
- [ ] Install Dev Container Extension
- [ ] Reopen Container
- [ ] Retrieve development.key from 1Password > {CLIENT} > Engineering
    `echo "DEVELOPMENTKEY" > ./config/credentials/development.key`
- [ ] Set up Config
    `cp .envrc.docker.example .envrc`
    `cp .env.example .env`
cp .env.example .env
- [ ] Setup Databases
    `rails db:restore`
    `rails db:create:passport db:schema:load:passport db:migrate:passport`