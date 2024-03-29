# selfhosted ntfy.sh setup

https://ntfy.sh/

## start

    docker compose up -d

## to create users

    docker compose exec ntfy /bin/sh

### inside container:

#### add sender user with:

    ntfy user add flexget
    # password with max 72 characters!

    ntfy access flexget flexget write-only

#### add receiver user with:

    ntfy user add myself

    ntfy access myself flexget read-only

exit container

## Setup Android app

1. Install https://f-droid.org/en/packages/io.heckel.ntfy/
1. Change Default-Server under Settings
1. Settings > Manage Users > Add new user
1. subscribe a topic

## Send test push

    curl -u flexget -d "flexget topic test-message" $DESTINATION/flexget

---

See also:
* https://docs.ntfy.sh/install/
* https://docs.ntfy.sh/install/#docker
* https://docs.ntfy.sh/config/
* https://blog.alexsguardian.net/posts/2023/09/12/selfhosting-ntfy/
