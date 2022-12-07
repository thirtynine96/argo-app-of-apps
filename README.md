# argocd apps
Argo 사이트에서 보이는 app 들은 kind: Application 이다. (CRD)
1. Helm repo 를 이용해서 argocd 를 설치한 경우
   * 설치
   ```
   cd argo-cd
   helm install -n argocd ds-argocd argo/argo-cd 
   ```
   * 업그레이드 (app of apps 적용)
   ```
   helm upgrade -n argocd ds-argocd argo/argo-cd -f ../argo-app-of-apps/values_root.yaml
   ```
2. ArgoCD Chart 를 바이너리형태로 다운로드 해서 설치한 경우
   * 설치
   ```
   helm install -n argocd ds-argocd .
   ```
   * 업그레이드
   ```
   cd argo-app-of-apps
   helm upgrade -n argocd ds-argocd . -f values_root.yaml
   ```
3. argo-apps 디렉토리의 application crd 명세를 하나의 파일로 작성필요



