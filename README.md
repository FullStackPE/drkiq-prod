Dockerizing a Ruby on Rails Application (production version)
============================================================

# Generic setup

- Clone the project:

        git clone https://github.com/FullStackPE/drkiq-prod.git
        cd drkiq-prod

- Let's try to run everything. Spoiler: it will fail!

        docker-compose up

- You should now notice a few errors related to the db. That's because we still didn't create it. So let's stop everything (`CTRL C`) and set up the db:

        sudo docker-compose run --user "$(id -u):$(id -g)" drkiq rake db:reset
        sudo docker-compose run --user "$(id -u):$(id -g)" drkiq rake db:migrate

- Try to run again

        docker-compose up

- In your browser, you should find everything at `http://localhost:8000`.
