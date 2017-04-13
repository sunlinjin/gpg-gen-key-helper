# gpg-gen-key-helper

Helper script to ease generating GPG keys.

## Requirements

* Debian-based systems:

```shell
apt-get install gnupg
```

* MacOS X:

```shell
brew install gnupg
```

## Usage

Just run:

```shell
bash ./gen-key.sh
```

and answear couple of questions. After successful run you should have three files in dir:

*  rsa-4096.pub - public key
*  rsa-4096.sec - private key

(and if you answear Y to export)
*  public.key.asc - public key in ASCII format

## Known issues

(Linux-only)

If GnuPG complains about small entropy, you can check its "quality":

```shell
cat /proc/sys/kernel/random/entropy_avail
```

If it returns anything less than 100-200, you have a problem. You can solve that by installing haveged - a simple entropy daemon.

```shell
apt-get install haveged
```

(MacOS-only)

Seems like a MacOS X GnuPG version is really fucked-up and does not generate private key in current dir. Or sth like that. I don't know, and as long as I use Linux - I DON'T CARE. :-)
