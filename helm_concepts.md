# Helm 
This file explains about helm commands and concepts. Helm uses the `Go` programming languages text template engine. 

### Helm repo 

Helm repo contains the packages which we used to deploy. 

```bash 
helm install apache bitnami/apache --namespace front-end 
helm upgrade apache bitnami/apache --namespace front-end 
helm rollback apache 1 --namespace front-end 
helm uninstall apache --namespace front-end 
```

![Helm rpo](Markdown/image-2.png)

#### Advantages of using helm:
-   Helm maintains revision history
-   Dynamic configuration using values.yaml. 
-   Consistency.
-   Life cycle hooks. 
-   Charts are secured, signed and verified.  

#### Helm popular repo 

```bash 
#popular repo for helm 
https://bitnami.com/stacks

# source of the charts 
https://github.com/bitnami/charts
```

### Work with repo:

```bash
#list the repo 
helm repo list 

#add the repo
helm repo add bitnami https://charts.bitnami.com/bitnami 

#search repo 
helm search repo apache 

#shows latest version
helm search repo mysql 

#see all versions
helm search repo mysql --version 

##remove repo
helm repo remove bitnami 
```

### Helm custom values 

```bash 
helm install mydb bitnami/mysql -f values.yaml 
helm upgrade mydb bitnami/mysql --reuse-values 
```

### Release records 

When we do `kubectl get secrets` command we will get secrets, this will have entire information about the installations. When we do `helm uninstall name` the secrets also will be get deleted. You can also use `helm uninstall name --keep-history` 

![secrets](Markdown/image-3.png)

```bash 
#list the helm charts 
helm ls 

#get the secrets 
kubectl get secrets 



###  example of go programming syntax:
```bash
    {{ include "firstchart.fullname" . }}
```

### chart.yaml

maintainers, version, keywords, application version, 

### 

### template 

-   Responsible for creating final manifest. 
- {{.Values.mysqlService.type}} [Google co syntax]
Under below if you don't need any file you can remove it. 

- deployment.yaml - 1
- hpa.yaml - Based on the condition it will be enabled. 
- ingress.yaml - Based on the condition it will be enabled.
- service.yaml 
- serviceaccount.yaml

-  _helpers.tpl file [It have funcations and methods]

- include method 
- explanation about . 


- values.yaml   

### Helm package 

```bash 
    helm package <chart-name> 
    helm package firstchart ---dependencies 
    helm package firstchart --destination/ -d /Users/venkat/path/to/directory 
```

- .helmignore    *.txt  This file used to ignore the files on helm package. 

### Helm lint command 

```bash 
    helm lint <chart-name>
```

- Zero exit code says success, Non-zero exit code shows the error. 

