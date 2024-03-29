
# start

    docker compose up -d

## to create users

    docker compose exec ntfy /bin/sh

### inside container run:

#### add sender user

    ntfy user add flexget
    # password with max 72 characters!

    ntfy access flexget flexget write-only

#### add receiver user

    ntfy user add myself

    ntfy access myself flexget read-only

exit container

# Send test push

curl -u flexget -d "flexget topic test-message" $DESTINATION/flexget


See also:
* https://docs.ntfy.sh/install/
* https://docs.ntfy.sh/install/#docker
* https://docs.ntfy.sh/config/
* https://blog.alexsguardian.net/posts/2023/09/12/selfhosting-ntfy/
