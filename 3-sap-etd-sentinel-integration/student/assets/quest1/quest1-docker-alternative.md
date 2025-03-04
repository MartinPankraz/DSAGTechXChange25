# Alternative Evilginx installation options

In case the Docker approach is not for you, you may install from the available binary or build from source.

## Prerequisite

Find the documentation for the tool [here](https://help.evilginx.com/docs/intro).

Install [git](https://git-scm.com/downloads) if you haven't already.

```bash
git clone https://github.com/kgretzky/evilginx2.git
```

> [!TIP]
> If you have not installed a Git client, you can also go directly to the [Evilginx3 repo](https://github.com/kgretzky/evilginx2), click on *Code* and *Download ZIP*. Once the ZIP file is downloaded extract it to your virtual machine. 

> [!IMPORTANT]
> Many of you will run into Defender detections with the executable upon [download](https://github.com/kgretzky/evilginx2/releases). Consider building the tool from source in such cases.

## Step1 - Option 1: Build from source

- Install [golang](https://go.dev/doc/install)
- Restart your terminal and verify the installation with `go version` command.

```bash
cd evilginx2
.\build_run.bat
```

- Allow Access on subsequent Defender firewall prompt like a vigilante in the making.

## Step1 - Option 2: Install the pre-built version

In case you are lucky you can follow the normal install steps:

- Get the latest release from the [releases page](https://github.com/kgretzky/evilginx2/releases) (Assets -> evilginx*-64bit.zip) and follow the [quick start guide](https://help.evilginx.com/docs/getting-started/deployment/local).

- Allow Access on subsequent Defender firewall prompt like a vigilante in the making.

## Step2 - Deal with EvilGinx's certificate

- Find the root certificate in the `User` folder (%USERPROFILE%\\.evilginx\crt) and install it on your machine.
![find root certificate](assets/quest1/install-certificate.png)

- Add this certificate to the Trusted Root Certificate Authorities store of the Current User. Otherwise, you will get a certificate error when accessing the phishing page.

You may need to restart your machine for the changes to take effect.

## Step3 - Create or retrieve a phishlet for your scenario

We will use a sample phishlet for M365 shared by [Jan Bakker](https://github.com/BakkerJan/evilginx3/blob/main/microsoft365.yaml).

* Download it or find it in the `assets` folder of this repository [here](assets/m365-phishlet.yaml).
* Place the phishlet by placing it in `.\evilginx2\phishlets` folder of the prior cloned repos `evilginx2`. It contains the example phishlet.

Restart your instance for the changes to take effect like so:

```bash
q
build_run.bat
```

- Verify the M365 phishlet is now showing up.
![new phishlet](assets/quest1/new-phishlet.png)

> [!TIP]
> Always check for updates on the phishlets and the tool itself. Things are changing rapidly in the security world.
