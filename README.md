## G-Core Labs DNS v2 API provider for octoDNS

An [octoDNS](https://github.com/octodns/octodns/) provider that targets [G-Core Labs DNS](https://gcorelabs.com/dns/).

### Installation

#### Command line

```
pip install octodns_gcore
```

#### requirements.txt/setup.py

Pinning specific versions or SHAs is recommended to avoid unplanned upgrades.

##### Versions

```
# Start with the latest versions and don't just copy what's here
octodns==0.9.14
octodns_gcore==0.0.1
```

##### SHAs

```
# Start with the latest/specific versions and don't just copy what's here
-e git+https://git@github.com/octodns/octodns.git@9da19749e28f68407a1c246dfdf65663cdc1c422#egg=octodns
-e git+https://git@github.com/octodns/octodns-gcore.git@ec9661f8b335241ae4746eea467a8509205e6a30#egg=octodns_gcore
```

### Configuration

```yaml
providers:
  gcore:
    class: octodns_gcore.GCoreProvider
    # Your API key
    token: env/GCORE_TOKEN
    token_type: APIKey
    # or login + password
    #login: env/GCORE_LOGIN
    #password: env/GCORE_PASSWORD
    #auth_url: https://api.gcdn.co
    #url: https://dnsapi.gcorelabs.com/v2
    #records_per_response: 1
```

### Support Information

#### Records

GCoreProvider supports A, AAAA, NS, MX, TXT, SRV, CNAME, and PTR

#### Dynamic

GCoreProvider supports dynamic records.

### Development

See the [/script/](/script/) directory for some tools to help with the development process. They generally follow the [Script to rule them all](https://github.com/github/scripts-to-rule-them-all) pattern. Most useful is `./script/bootstrap` which will create a venv and install both the runtime and development related requirements. It will also hook up a pre-commit hook that covers most of what's run by CI.
