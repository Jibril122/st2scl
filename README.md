# st2scl

## Car rental service

https://github.com/charroux/st2scl/tree/main/rentalService

```
curl --header "Content-Type: application/json" --request GET http://localhost:8080/cars
```

```
curl --header "Content-Type: application/json" --request PUT --data '{"begin":"4/11/2024","end":"20/11/2024"}' 'http://localhost:8080/cars/11AA22?rent=true'
```

### Coding rules

Exception HTTP Handler: https://github.com/charroux/st2scl/blob/main/rentalService/src/main/java/com/example/rentalService/web/CarNotFoundException.java

Logger: https://github.com/charroux/st2scl/blob/main/rentalService/src/main/java/com/example/rentalService/web/RentalWebService.java

### Launch a workflow when the code is updated

The script is there: https://github.com/charroux/st2scl/blob/main/.github/workflows/acttions.yml

Create a new branch:
```
git branch newcarservice
```
Move to the new branch:
```
git checkout newcarservice
```
Update the code and commit changes:
```
git commit -a -m "newcarservice"
```
Push the changes to GitHub:
```
git push -u origin newcarservice
```
Create a Pull request on GitHub and follow the workflow.

Merge the branch on Github is everything is OK.

Then pull the new main version:

```
git checkout main
```
```
git pull origin main
```

If necessary delete the branch:

```
git branch -D newcarservice
```
```
git push origin --delete newcarservice
```

### Créer image docker

Ajouter un Dockerfile: https://github.com/charroux/st2scl/blob/main/rentalService/Dockerfile

Créer une image docker:
```
docker build -t rental .   
```
Tester l'image:
```
docker run -p 8080:8080 rental   
```

Modifier le script du pipeline CI/CD
