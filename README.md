# Catalog API
REST API built end-to-end from scratch using the latest innovations from .NET 5, Docker, Kubernets, Post and Visual Studio Code. The API will be written in C#.

## 🚀 Technologies

This project was developed with the following technologies:

- [C Sharp](https://docs.microsoft.com/pt-br/dotnet/csharp/tour-of-csharp/)
- [ASP.NET Core](https://dotnet.microsoft.com/download/dotnet/5.0)
- [Docker](https://docs.docker.com/docker-for-windows/install/)
- [Kubernets](https://docs.docker.com/desktop/kubernetes/)
- [Postman](https://www.postman.com/downloads/)
- [VSCode](https://code.visualstudio.com/)
- [MongoDB](https://www.mongodb.com/pt-br)

## 🔥 How to install

```bash
# Clone this repository
$ git clone https://github.com/gabrielvieira1/Catalog.Api.git

# Go into the repository folder and install dependencies
$ cd Catalog.Api

# Run
$ dotnet restore

# Go to the repository folder and build the docker file
$ cd Catalog.Api

$ docker build -t catalog:v1 .

# You need to be logged in to the docker
$ docker tag catalog:v1 yourUserDocker/catalog:v1

$ docker push yourUserDocker/catalog:v1

# Open the project with VScode, in the Catalog.Api project in the Kubernets folder edit the catalog.yaml file
# On line 16 in image change to yourUserDocker/catalog:v1
image: yourUserDocker/catalog:v1

# Go to the repository folder and create your secrets kubernets
$ cd kubernetes

$ kubectl create secret generic catalog-secrets --from-literal=mongodb-password='YourPassword'

# Run catalog.yaml and mongodb.yaml files
$ kubectl apply -f catalog.yaml

$ kubectl apply -f mongodb.yaml

# Check status of pods
$ kubectl get pods

# Your pods were more or less like this
NAME                                  READY   STATUS    RESTARTS   AGE
catalog-deployment-55c868ffdb-rmz8l   0/1     Running   0          28s
mongodb-statefulset-0                 1/1     Running   0          15s

# Now on Postman test the Api, for example:
GET - http://localhost:31111/items
POST - http://localhost:31111/items
```

## 🤔 How to contribute

- Make a fork;
- Clone the forked repository;
- Create a branch with your feature: `git checkout -b my-feature`;
- Commit changes: `git commit -m 'feat: My new feature'`;
- Make a push to your branch: `git push -u origin my-feature`;
- Create a PR from your branch to my branch.

After merging your receipt request to done, you can delete a branch from yours.

## :memo: License

This project is under the MIT license. See the [LICENSE](LICENSE) for details.

Made with ♥ by Gabriel Vieira :wave: [Get in touch!](https://www.linkedin.com/in/bielvieira/)`