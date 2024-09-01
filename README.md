# zPodLibrary
zPodFactory official default library of components.

> [!NOTE]  
> This is the official public repository of components supported by zPodFactory.
> 
> It contains all the relevant information to deploy a VMware OVA into a zPod.
>  - `component_uid` which is the concatenation of `component_name` and `component_version` SHOULD be unique within a zPodFactory instance as it determines how to refer to a component when deploying a zPod from a profile, or adding a component to a zPod later on. (If you do not respect this requirement, you'll have database unique key constraints issues)
>  - `component_download_file_checksum` and `component_download_file_size` are mandatory to validate the file within the engine (If the checksum doesn't validate the file will be deleted, for the download file size it will be used to show download progress when using the `https` download engine)
>  - `component_deploy_govc_spec` should contain the full govc spec for deployment (you can leverage various zPodFactory variables to fill deployment variables such as `{{zpod_password}}`, `{{zpod_portgroup}}` and many others available to double check in the provided components)



You can also build your own zPodLibrary, private, public as long it is a Git repository as the update process consists of using git commands (git fetch/pull and updating every component JSON file in that repo whenever the `zcli library resync {library_name}` command is used.


- [zPod CLI - Manage library](https://zpodfactory.github.io/guide/admin/#manage-library)



> [!CAUTION]
> Since the Broadcom Acquisition, the `customerconnect` download engine isn't working anymore :-(
> 
> The only current way to enable a component is to either use the `https` download engine (it basically will leverage wget to fetch a component on a reachable server from your zPodFactory instance), or to use zPodFactory 0.7.2+ embedded `zcli component upload {filename}` feature depicted here:
>
> - [zPod CLI - Manage components](https://zpodfactory.github.io/guide/admin/#manage-components)


