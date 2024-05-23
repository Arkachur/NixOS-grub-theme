# NixOS-grub-theme

This is a fork of `xenlism/Grub-themes`, made specifically for an use-case in NixOS. To use this repo, you need to add the following to your `configuration.nix` file 
```nix
{ config, lib,  pkgs, ... }:

let
  xenlism-grub-theme = pkgs.fetchFromGitHub
  {
    owner = "Arkachur";
    repo = "NixOS-grub-theme";
    rev = "5309fdf51374af71a34a4caf9ee2f290a86c5a61";
    sha256 = "sha256-LNT1SKxQDvdHzsOCMSA0aTBM5TY3/ReLLVCVS+9hgh8=";
  };

in
{
  boot.loader.grub.theme = xenlism-grub-theme;
}
```

*Note:* the `rev` and thus `sha256` are hard coded for a specific version. I order to use the latest version (rn, the hardcoded is the latest one), use `nix-prefetch-git` to know about it.
```bash
nix-prefetch-git https://github.com/Arkachur/NixOS-grub-theme
```

Then fill up the required data.
