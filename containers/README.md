Artifactory and Registry do not require a Dockerfile. They can be built/run directly from the official image. Their dockerfiles were only needed to fix the time zone, which is not needed anymore since the optimization suggested by Jan Krag is working well.


create-homes.sh is used to create the data (home) directories for jenkins and artifactory, inside /opt/containers.

This was the directory originally used to hold home directories. But now the home / data directories for jenkins, artifactory and registry are relocated to /opt/containers.
Those directories (complete tree below /opt/containers must be owned by uid 1000 and gid 1000, irrespective of the user and group (1000) exist on the system or not.

.
├── artifactory
│   ├── backup
│   ├── data
│   └── logs
└── jenkins_home
└── registry


