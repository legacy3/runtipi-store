# Lumen

A private Lumina server that can be used with IDA Pro 7.2+.

[lumen.abda.nl](https://lumen.abda.nl/) runs this server.

You can read about the protocol research [here](https://abda.nl/posts/introducing-lumen/).

## Features

- Stores function signatures so you (and your team) can quickly identify functions that you found in the past using IDA's built-in Lumina features.
- Backed by PostgreSQL
- Experimental HTTP API that allows querying the database for comments by file or function hash.
- **NO TLS** - designed for use with reverse proxy setups

## Configuration

### Environment Variables

- **LUMEN_USER**: Username for Lumen authentication (recommended: 'guest')
- **LUMEN_PASS**: Password for Lumen authentication (recommended: 'guest')
- **NO_TLS**: Set to 'true' to disable TLS (configured by default)

### Database Configuration

Lumen uses PostgreSQL 15.1 Alpine for its database backend with the following default settings:

- Database: `lumina`
- User: `lumina`
- Password: `1`

### Ports

- **Main Application**: Port 1234 (Lumina protocol)
- **Additional Services**: Port 8082 (HTTP API)

## Configuring IDA Pro

### IDA Pro >= 8.1

#### Setup under Linux

```bash
#!/bin/sh
export LUMINA_TLS=false
$1
```

- Save as ida_lumen.sh, "chmod +x ida_lumen.sh", now you can run IDA using "./ida_lumen.sh ./ida" or "./ida_lumen ./ida64"

#### Setup under Windows

```batch
set LUMINA_TLS=false
%1
```

- Save as ida_lumen.bat, now you can run IDA using "./ida_lumen.bat ida.exe" or "./ida_lumen.bat ida64.exe"

#### Setup IDA

- Go to Options, General, Lumina. Select "Use a private server", then set your host and port and use your configured username and password (default: 'guest'/'guest'). Click on ok.

### IDA Pro < 8.1

You will need IDA Pro 7.2 or above in order to use _lumen_.

> The following information may get sent to _lumen_ server: IDA key, Hostname, IDB path, original file path, file MD5, function signature, stack frames & comments.

- In your IDA's installation directory open "cfg\ida.cfg" with your favorite text editor _(Example: C:\Program Files\IDA Pro 7.5\cfg\ida.cfg)_
- Locate the commented out `LUMINA_HOST`, `LUMINA_PORT`, and change their values to the address of your _lumen_ server.
- Add "LUMINA_TLS = NO" after the line with `LUMINA_PORT`.

Example:

```C
LUMINA_HOST = "192.168.1.1";
LUMINA_PORT = 1234
LUMINA_TLS = NO
```

## Storage

Application data is stored in the following directories:

- `/dockershare`: Application shared data directory
- `/postgres_data`: PostgreSQL database files

All data is automatically mapped to your Runtipi app data directory for persistence across container restarts.

## Health Monitoring

The PostgreSQL service includes built-in health checks using `pg_isready` to ensure database availability before starting dependent services.

---

Developed by [Naim A.](https://github.com/naim94a); License: MIT.
