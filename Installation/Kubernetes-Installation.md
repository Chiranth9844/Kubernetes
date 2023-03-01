# KUBERNETES-Installation

## Install and Set Up kubectl on macOS

For easy installation we use [Homebrew](https://brew.sh/) package manager. <br/>
  * Run the installation command:<br/>
    `brew install kubectl`<br/>
  * Test to ensure the version you installed is up-to-date:<br/>
     `kubectl version --client` <br/>
    
## Install minikube

  * Go to https://minikube.sigs.k8s.io/docs/start/ select the buttons according to the PC configurations<br/>
      run : `brew install minikube`<br/>
            
  * To start the minikube cluster we need container runtime or virtual machine manager pre-installed, in our case we use Docker<br/>
    (if docker is not yet installed go to https://www.docker.com/ for docker installation)<br/>
      run : `minikube start` this will take Docker as the default driver<br/>
    or<br/>
      run : `minikube start --driver docker` <br/>
  
   * We cancheck the status of the cluster by<br/>
     `minikube status`<br/>
    
   * To interact with our cluster<br/>
     `kubectl get po -A` <br/>
  
