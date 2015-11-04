# Building the Origin Metrics Docker Images

If you wish to build your own Origin Metric docker images, the easiest way is to use the `hack/build-images.sh` script.

This will allow you to build all the docker images, as well as optionally push those images out to a docker registry.

The following command will build locally all the Origin Metric docker images:

	cd hack
	./build-images.sh --prefix=openshift/origin- --version=devel
	
If you wish to optionally build and push your images to a registry, you will just need to add the `--push` option

	cd hack
	./build-images.sh --prefix=openshift/origin- --version=devel --push


The `--prefix` value is used to specify a prefix to the docker image and the `--version` value is used to specify the version tag for the resulting docker images.

>:star: **Note** :
>You will need to know the `--prefix` and `--version` values when you go to use the deployer. The `IMAGE_PREFIX` and `IMAGE_VERSION` template parameters have to match exactly the values specified for `--prefix` and  `--version`

For instance, as with the above command, a prefix of `openshift/origin-` and version `devel` will create the following docker images:

	openshift/origin-metrics-deployer
	openshift/origin-metrics-heapster
	openshift/origin-metrics-cassandra
	openshift/origin-metrics-hawkular-metrics
