# Docker instructions for Kali Linux

Kali Linux is an Advanced Linux distribution used for Penetration Testing, Ethical Hacking and network security assessments.

* Install [PowerShell 7.4+](https://learn.microsoft.com/powershell/scripting/overview). It runs on any OS.
* [Install Docker](https://docs.docker.com/desktop/install/windows-install/) for your OS.
* Continue your setup [here](../student/quest1.md#step-1a-build-image-from-dockerfile-and-run-container-on-your-local-machine) and run the commands or scripts depending on your chosen container runtime.

## Podman as alternative to Docker

* [Install Podman](https://podman.io/)

* Run below commands in sequence to pre-configure podman.

```bash
podman machine init
podman machine set --rootful
podman machine start
```

* Continue your setup [here](../student/quest1.md#step-1a-build-image-from-dockerfile-and-run-container-on-your-local-machine) and run the commands or scripts depending on your chosen container runtime.

> [!TIP]
> The scripts are meant for initial execution. When revisiting the container after a break or similar, run the following from within the container to reach operational status again:
>
> ```bash
> docker start -ia my-evilginx-container
> ```
> or
> ```bash
> podman start -ia my-evilginx-container
> ```
>
> This command takes you directly to the Evilginx command line interface.

> [!IMPORTANT]
> When restarting the config process, you will need to download the required certificate, and repeat config steps again. Run the command `.\get-crt.ps1` from the git repos in your terminal outside of the EvilGinx process.