# Seeds

Utility to generate the seeds.txt list that is compiled into the client
(see [rebelcoin/rebelcoinseeds.h](/rebelcoin/rebelcoinseeds.h) and other utilities in [deploy/seeds](/deploy/seeds)).

Be sure to update `PATTERN_AGENT` in `makeseeds.py` to include the current version,
and remove old versions as necessary (at a minimum when GetDesirableServiceFlags
changes its default return value, as those are the services which seeds are added
to addrman with).

The seeds compiled into the release are created from poolers's DNS seed data, like this:

    python3 makeseeds.py < seeds_main.txt > nodes_main.txt
    python3 generate-seeds.py . > ../../rebelcoin/rebelcoinseeds.h

## Dependencies

Ubuntu:

    sudo apt-get install python3-dnspython
