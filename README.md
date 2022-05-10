# A CMS RPC Currents monitor

## Requirements

Python 3 is required.

## Quick Start

You should be running this within CERN network. One can use `lxplus` or `sshuttle`.

More info on sshuttle: https://github.com/sshuttle/sshuttle

Basic usage: `sshuttle --dns -r CERN_LOGIN@lxplus.cern.ch 0/0`

## Install the Oracle Database Instant Client

So far, tested only with version 19.8.

https://www.oracle.com/database/technologies/instant-client.html
place the instant client inside `/lib`.

Setup a virtual environment (only once).

```console
python3 -m venv ./venv
```

Load the virtual environment.

```console
source ./venv/bin/activate
```

Install needed packages.

```console
python3 -m pip install -r requirements.txt
```

Configure the dates at the main script `cms_rpc_monitor.py`. Look for the lines below

```python
initial_date = datetime.datetime(2022, 1, 1).isoformat().replace("T", " ")
end_date = datetime.datetime(2023, 5, 28).isoformat().replace("T", " ")
```

Run the tool.

```console
./cms_rpc_monitor.py HERE_GOES_THE_CMS_RPC_R_PASSWORD_IN_A_SINGLE_STRING
```
