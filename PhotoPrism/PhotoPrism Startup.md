
https://docs.photoprism.app/developer-guide/setup/

#### Tensorflow
Tensorflow has to be installed the c way: https://www.tensorflow.org/install/lang_c
**its important to install 1.15, not latest. When latest pointer exception is thrown**


#### Github issues that helped

https://github.com/photoprism/photoprism/issues/970
https://github.com/photoprism/photoprism/discussions/4247
https://github.com/tensorflow/tensorflow/issues/20440
env vars: https://github.com/photoprism/photoprism/issues/418
paste of the env vars
	[Unit]
	Description=PhotoPrism
	
	[Service]
	Environment="HOME=/var/lib/private/photoprism"
	Environment="LOCALE_ARCHIVE=/nix/store/zcsy6v9ivwld6h4i1aqggn0zfk602dls-glibc-locales-2.30/lib/locale/locale-archive"
	Environment="PATH=/nix/store/v8v81amvwqf73m6mkg5vgijq4gjkpvg3-libtensorflow-1.14.0/bin:/nix/store/x0jla3hpxrwz76hy9yckg1iyc9hns81k-cor...
	Environment="PHOTOPRISM_ADMIN_PASSWORD=photoprism"
	Environment="PHOTOPRISM_DARKTABLE_PRESETS=false"
	Environment="PHOTOPRISM_DATABASE_DRIVER=sqlite"
	Environment="PHOTOPRISM_DEBUG=true"
	Environment="PHOTOPRISM_DETECT_NSFW=false"
	Environment="PHOTOPRISM_EXPERIMENTAL=false"
	Environment="PHOTOPRISM_HTTP_HOST=127.0.0.1"
	Environment="PHOTOPRISM_HTTP_PORT=2342"
	Environment="PHOTOPRISM_JPEG_QUALITY=90"
	Environment="PHOTOPRISM_JPEG_SIZE=7680"
	Environment="PHOTOPRISM_PUBLIC=false"
	Environment="PHOTOPRISM_READONLY=false"
	Environment="PHOTOPRISM_SETTINGS_HIDDEN=false"
	Environment="PHOTOPRISM_SITE_AUTHOR="
	Environment="PHOTOPRISM_SITE_CAPTION=Browse Your Life"
	Environment="PHOTOPRISM_SITE_DESCRIPTION="
	Environment="PHOTOPRISM_SITE_TITLE=PhotoPrism"
	Environment="PHOTOPRISM_SITE_URL=http://localhost:2342/"
	Environment="PHOTOPRISM_STORAGE_PATH=/var/lib/private/photoprism/storage"
	Environment="PHOTOPRISM_THUMB_FILTER=lanczos"
	Environment="PHOTOPRISM_THUMB_SIZE=2048"
	Environment="PHOTOPRISM_THUMB_SIZE_UNCACHED=7680"
	Environment="PHOTOPRISM_THUMB_UNCACHED=false"
	Environment="PHOTOPRISM_UPLOAD_NSFW=true"
	Environment="TZDIR=/nix/store/8cz89zavyrm2bdrgkx4l66s5c7nx12dr-tzdata-2019c/share/zoneinfo"
	
	DynamicUser=yes
	ExecStart=/etc/nixos/bin/photoprism start
	ExecStop=/etc/nixos/bin/photoprism stop
	ReadWritePaths=/var/lib/private/photoprism
	Restart=always
	RestartSec=10
	StateDirectory=photoprism
	Type=simple
	WorkingDirectory=/var/lib/private/photoprism
