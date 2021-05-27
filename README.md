# GraphQL with Laravel

This project is to understand how graphql works and do a basic implementation with laravel framework

## Requirement

- php 8
- composer
- node
- MYSQL

## Steps

- Clone the repo
- copy `.env.example` to `.env`
- update necessary values in `.env` file
- Create the database in MySql

## Run

- `composer install`
- `php artisan migrate`
- `php artisan serve`
- open browser and goto `localhost:8000/graphiql`

## Example query in graphiql

- To get list of quests

    {
      quests {
        title
      }
    }

- To get quest by id

    {
      quest(id: 11) {title}
    }

- To create new Quest

    mutation{
      createQuest(
        title: "some title again",
        description:"asdadad adssadd asa dads sadasdad",
        reward:300,
        category_id:2
      ) {id, title, category{title}}
    }

- To update a quest by id

    mutation{
      updateQuest(
        id:11,
        title: "SOME TITLE UPDATED",
        description:"asdadad adsa dads sadasdad",
        reward:400,
        category_id:1
      ){id, title, category{id, title}}
    }

- To delete quest by id

    mutation{
      deleteQuest(id:12)
    }
