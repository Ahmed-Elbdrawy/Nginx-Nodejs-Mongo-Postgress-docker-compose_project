## Prerequisites
```
To deploy the app you need to install docker, docker-compose

add new record in /etc/hosts "127.0.0.1 elbdrawy.com"
```

### Installing

To get the app running

```
git clone https://github.com/Ahmed-Elbdrawy/Nginx-Nodejs-Mongo-Postgress-docker-compose_project.git
docker-compose up -d --force-recreate
```

### Testing
- open https://elbdrawy.com  


### TO create a self-signed cert  and RUN APP
```
1 - run './self-signed.sh'  you cane change domain name ex: elbdrawy in file
2 - run 'docker-compose up '
3 - Open Browser enter http://elbdrawy.com Or https://elbdrawy.com
```

### GraphQL deep dive

Run `yarn start:dev` to test

Use `yarn start` in production setting

### Sample query and mutation
```

query MyContests {
  me(key: "0000") {
    id
    email
    fullName
    contestsCount
    namesCount
    votesCount
    contests {
      id
      title
      code
      status
      description
      createdAt
      names {
        label
        createdBy {
          fullName
        }
      }
    
    }
    activities {
      ... on ContestType {
        header: title
      }
      ... on Name {
        header: label
			}
    }
  }
}

mutation AddNewContest($input: ContestInput!) {
  AddContest(input: $input) {
    id
    code
    status
    description
  }
} 

```
