<!-- GETTING STARTED -->
### Prerequisites

This is an example of how to list things you need to use the software and how to install them.

  ```sh
  echo 'export ISTIO_VERSION="1.5.2"' >> ${HOME}/.bash_profile
  source ${HOME}/.bash_profile
  curl -L [https://istio.io/downloadIstio](https://istio.io/downloadIstio) | sh -
  cd istio-*
  sudo cp -v bin/istioctl /usr/local/bin/
  ```

### Installation

  ```sh
  # Generating istio YAML file
  istioctl profile dump <ISTIO_PROFILE_NAME> > raw_demo_profile.yaml # We use demo profile
   
  # Convert istio YAML file to k8s YAML file
  istioctl manifest generate  -f raw_demo_profile.yaml > istio-configuration.yaml

  # Move "istio-system" namespaces creation to the top of the file
  # Remove "istio-gateway" creation from the main(istio-configuration.yaml) YAMl to istio-gw-configuration.yaml so you can manage your ingress configurations
  ```
