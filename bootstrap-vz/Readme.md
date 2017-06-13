# Bootstrap-vz

Simple debian builder based on a yaml manifest.

## Requirements

Python2 as default is required, as well as:
- kpartx
- debootstrap
- parted

The recommended installation methodology is:
```sh
cd /tmp
virtualenv -p `which python2` vz
cd vz
. bin/activate
git clone -b working https://github.com/exy13/bootstrap-vz
cd bootstrap-vz
sudo pip install .
sudo ./bootstrap-vz /path/to/jessie.yml
```

## Configuration

The following variables should be set-up in the manifest:
- name: The name of the resulting image
- workspace: Path to the final image folder, /tmp is advised for faster
	building.
- hostname: The VMs hostname.
- root/size: The size of the / partition.
- packages/install: list of needed packages.
- root_password: Self-explanatory.
- commands: A public key may be added in the same way the example one is
	provided. This will allow an immediate ssh connection once the VMs ip is
	known.
