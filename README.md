Install the Packages using Ansible  Step by Step

 Step 1 : Install the git Latest version

        apt name:git state:present

Step 2:   Install the Docker latest Version

         apt name:docker state:present

Step 3:install the docker compose latest version

        apt name:docker-compose state:latest

Step 4:   install the openssl latest version

         apt name:openssl state:latest

Step 5:    install  the node version

         apt name:nodejs state=latest

Step 6:  install the nvm version

      Step 6.1 :  Install nvm dependencies
          apt: name="{{ item }}"
          with_items:
            - curl
            - build-essential
            - libssl-dev

      Step 6.2 : Install nvm
           git: repo=https://github.com/creationix/nvm.git dest=~/.nvm

       Step 6.3 : Source nvm in ~/.profile
               lineinfile: >
                dest=~/.profile
                line="source ~/.nvm/nvm.sh"
                create=yes
~
