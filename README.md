# Brincando com Kubernetes (K8's)
Neste repositório vou seguir um tutorial de como usar kubernetes para lançar uma aplicação em python (3.7).
## Requisitos
1. Instalar o [Docker Desktop](https://hub.docker.com/editions/community/docker-ce-desktop-windows) e habilitar o kubernetes.
2. Instalar a versão python 3.7 para testar o servidor.
3. Instalar no python o FLASK, que é um framework usado para construir aplicações web em python.
`pip install Flask`
4. Baixar a imagem docker do [python](https://hub.docker.com/_/python/) para criar o container.

## Passos para lançar o cluster
 1. Execute o script main.py
`python3 main.py`   
 2. Agora verifique se a aplicação está funcionando no browser.
[http://localhost:5000](http://localhost:5000)
 3. Agora é a hora de criar o conteiner da aplicação, esta etapa irá usar o Dockerfile para configurar sua app na imagem.
 
```docker build -f Dockerfile -t hello-python:latest```

 4. Rode seu container e agora tente abrir sua aplicação na porta criada para o container.
`docker run -p 5001:5000 hello-python`

[http://localhost:5001](http://localhost:5001)

 5. Com o conteiner funcionando agora vamos criar o cluster:
```kubectl apply -f deployment.yaml```
### 6. Tudo pronto, tente abrir sua applicação na porta do cluster, verifique a porta no arquivo 'deployment.yaml'.
(É a primeira porta do arquivo, no meu ultimo commit foi a 7000)

Caso o cluster seja criado e você não consiga encontrar o localhost:port do cluster, altere a porta no deploymente.yaml e refaça o passo 5.

## Links úteis
Site referência [Kubernets com python](https://kubernetes.io/blog/2019/07/23/get-started-with-kubernetes-using-python/).

