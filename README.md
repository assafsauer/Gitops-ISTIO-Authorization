# Continues authorization polIcies with argo CD.

####  The idea behind this respositroy is to outlines a continuous delivery approach that combines together Gitops and Devsecops that results as automation of authorization polIcies for all services in a namespace.

```diff
i used the authorization automation code from my Istio-Security-Mesh-Automated repository: 
https://github.com/assafsauer/Istio-Security-Mesh-Automated.
i copied the code to the k8s-manifest folder , so ArgoCD can track changes in the manifest 
and deploy the policies autmaticly ,based on code commit.

```
![image](https://user-images.githubusercontent.com/22165556/128327771-e1d3aa51-68f9-429b-907d-81db6d1b583f.png)

```diff

so how does it works ?

1) Developer commit/push code ,  CI/CD is being triggered 
3) as part of the continues security , Developer will execute the auth-main.py 
4) the authorization policies being created in the /k8s-manifest/manifest/auth folder (argoCD path folder).
5) Developer commit/push 
6) Argo CD track updates to branches to a specific version of manifests at a Git commit. 
argo CD will automaticly deploy the authorization policies  in the specified target environments/namespec. 
```

![image](https://user-images.githubusercontent.com/22165556/128159514-bf37e9e6-14a6-44a6-9a8e-20e8f402213e.png)

 I added a video that shows in more details the configuration steps.

[![IMAGE ALT TEXT HERE](https://img.youtube.com/vi/c3GgOXPz3fQ/0.jpg)](https://www.youtube.com/watch?v=c3GgOXPz3fQ)



Demo link: https://youtu.be/c3GgOXPz3fQ
