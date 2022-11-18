# docker-302
This image accepts http/https connections and responds with an http code 302 
redirect. It uses traefik so that https connections are legitimately signed.

# Build and deploy
    git clone github.com/jeffre/docker-302
    cd docker-302
    cat <<< EOF > .env
        EMAIL='certuser@example.com'
        REGEX='^https?://[^/]*/?(.*)'
        REPLACEMENT='https://example.com/$1'
    EOF
    docker compose up -d