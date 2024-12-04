# Mono-Repo-Setup

Nx Mono Repo Setup

## Steps

1. PNPM Workspace setup

    [Refrence](https://fazalerabbi.medium.com/monorepo-using-pnpm-workspaces-cb23ed332127)

   1. PreRequest Install
      1. `NPM` (Node Package Module)

         ```sh  
         #install npm globally 
         npm install -g npm  
         #Update npm globally 
         npm update -g npm
         ```

   2. *Install `pnpm`*: Start by installing pnpm globally if you haven’t already:

      ```sh
      #install PNPM 
      npm install -g pnpm
      #update PNPM 
      npm update -g pnpm
      ```

   3. *Initialize a Workspace*: Create a new directory for your monorepo and initialize a pnpm workspace:

      ```sh
      mkdir <pnpm-monorepo-workspace-name >
      cd pnpm-monore<pnpm-monorepo-workspace-name >
      pnpm init
      pnpm config set ignore-workspace-root-check true
      ```
   
   4. *Configure the Workspace*: Create a `pnpm-workspace.yaml` file in the root of your monorepo to define the packages in the workspace:

      ```yaml
      packages:
         # executable/launchable applications
         - 'apps/*'
         # all packages in subdirs of packages/ and components/
         - 'packages/*'
         # all the cofign in the config
         - 'configs/*'
      ```

   5. *Create Applications*: Create apps for react and nest apps. And packages for re-useable libraries:

      ```sh  
      mkdir apps
      mkdir packages
      mkdir config
      ```

   6. *Create `.npmrc` Node Package Manager Registry* :  create the files at root of project.json

      ```sh 
      code .npmrc
      ```

      add this in the `.npmrc` file

      ```sh 
      ignore-workspace-root-check=true  
      ```

   7. *Add Nx as a development dependency* :

      ```sh 
      pnpm add -D nx
      ```

2. *Setup `NX` Workspace Mono Repo* :

   1. *Run the Nx initialization command:*

      ```sh 
      npx nx init
      ```

   2. 
