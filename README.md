# st2scl

## Car rental service

https://github.com/charroux/st2scl/tree/main/rentalService

```
curl --header "Content-Type: application/json" --request GET http://localhost:8080/cars
```

```
curl --header "Content-Type: application/json" --request PUT --data '{"begin":"4/11/2024","end":"20/11/2024"}' 'http://localhost:8080/cars/11AA22?rent=true'
```

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
Move to the main branch:
```
git checkout main
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

### Docker

Create a Dockerfile in the code folder: https://github.com/charroux/st2scl/blob/main/rentalService/Dockerfile

Build a Docker image:
```
docker build -t rentalservice .      
```
Run the container:
```
docker run -p 4000:8080 rentalservice    
```
Then check in your browser:
```
http://localhost:4000/cars
```
