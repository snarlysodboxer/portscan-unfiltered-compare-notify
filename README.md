# portscan-compare-notify
Use Golang to parse and notify about Nmap results compared to a list of expected ports

#### Usage
###### Set the following environment variables, and run:
* HOST=me.example.com
* EXPECTED_PORTS="22 80 443"
* PARALLELISM=1024 # Nmap --min-parallelism
* PORT_RANGE="1-65535"
* TO_ADDRESSES="my_addy@example.com my_other_addy@example.com"
* FROM_ADDRESS=portscan@me.example.com
* SMTP_SERVER_ADDRESS=smtp.gmail.com:587
* SMTP_USER_ADDRESS=my_addy@example.com
* SMTP_PASSWORD=my_pass

E.G. `HOST=me.example.com EXPECTED_PORTS="22 80 443" PARALLELISM=1024 TO_ADDRESS=my_addy@example.com FROM_ADDRESS=portscan@me.example.com SMTP_SERVER_ADDRESS=smtp.gmail.com:587 SMTP_USER_ADDRESS=my_addy@example.com SMTP_PASSWORD=my_pass ./scan`

E.G. using Docker
```
docker run --rm \
  --env HOST=me.example.com \
  --env EXPECTED_PORTS="22 80 443" \
  --env PARALLELISM=1024 \
  --env PORT_RANGE="1-65535" \
  --env TO_ADDRESSES=my_addy@example.com \
  --env FROM_ADDRESS=portscan@me.example.com \
  --env SMTP_SERVER_ADDRESS=smtp.gmail.com:587 \
  --env SMTP_USER_ADDRESS=my_addy@example.com \
  --env SMTP_PASSWORD=my_pass \
  snarlysodboxer/portscan-compare-notify:latest
```

TODO
* Account for unshown ports that are 'closed'
* Document better
* Ensure needed settings are set and warn and raise if not.
