# 🌐 SocialDevs Frontend - GitOps Deployment

Este directorio contiene los manifiestos Kubernetes necesarios para desplegar la aplicación frontend de SocialDevs (SPA Vue.js + Nginx) usando GitOps con ArgoCD.

---

## 📁 Estructura

```bash
apps/
└── frontend/
    ├── deployment.yaml         # Despliegue del contenedor con imagen de Docker Hub
    ├── service.yaml            # Servicio Kubernetes (ClusterIP)
    ├── ingressroute.yaml       # Traefik IngressRoute para exponer el frontend
    └── kustomization.yaml      # Declaración Kustomize para ArgoCD
```

## 📦 Imagen Docker

- **Repositorio:** `vhgalvez/socialdevs-public-frontend`
- **Tag usado:** `v1.0.0`
- **Docker Hub:** [https://hub.docker.com/r/vhgalvez/socialdevs-public-frontend](https://hub.docker.com/r/vhgalvez/socialdevs-public-frontend)

---

## 🔗 URL Esperada (con Traefik)

La aplicación se expone en:


> Si usas un dominio real o Cloudflare, modifica `ingressroute.yaml` según corresponda.

---

## 🚀 Deploy con ArgoCD

1. Conecta este repositorio a ArgoCD (en la interfaz Web o vía `argocd` CLI).
2. Crea un `Application` apuntando a:

```yaml
repoURL: https://github.com/vhgalvez/socialdevs-gitops
targetRevision: HEAD
path: apps/frontend
