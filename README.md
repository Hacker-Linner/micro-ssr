# Micro SSR

### Deploy

```sh
helm install micro-ssr ./micro-ssr -f values.yaml -n micro-ssr
helm uninstall micro-ssr -n micro-ssr

helm install micro-ssr-home ./micro-ssr -f values-home.yaml -n micro-ssr
helm install micro-ssr-about ./micro-ssr -f values-about.yaml -n micro-ssr
```