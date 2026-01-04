# Helm 
This file explains about helm commands and concepts. 

### chart.yaml

maintainers, version, keywords, application version, 

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


