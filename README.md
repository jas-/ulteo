# Ulteo-OVD patch
This patch will implement CAS authentication redirection as the current implementation does not work properly.

# How to
In order for this patch to work properly you must first have a working installation.

# Create backup
I strongly recommend creating a backup of the current Ulteo-OVD CAS module implementation. You can do so from a command line like so.

```%> tar zxvf ~/ulteo-backup.tgz /usr/share/ulteo```

# Purge
Next you will need to completely remove the current CAS folder from the session manager like so.

```%> rm -frv /usr/share/ulteo/sessionmanager/PEAR/CAS*```

# Download
Now download the latest patch from here.

```git clone https://github.com/jas-/ulteo.git```

# Apply the patch
To apply the patch you must be in the ulteo directory, this command will perform everything you need for the patch to work.

```%> cd /usr/share && patch -p0 < ulteo-latest-cas.patch```

# Configure Ulteo-OVD
Now you will need to configure Ulteo using the administrative panel to use CAS as an authentication module.

# Create dynamic group
In order for CAS to work you will need a dynamic group added to the current publication of allowed software as well. Once this is done CAS authentication should work without problems.

# Bugs
Please let me know if you run into problems as this patch was somewhat rushed at the time of this writing.