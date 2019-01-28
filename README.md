# types

```gql
type User {
    _id: ObjectID
    username: String
    email: String
    name: {
        first: String
        last: String
    }
    roles: [String]
    cinvir: [String]
    properties: [Property]
    nationalities: [String]
    security: {
        access_tokens: [AccessToken]
    }
    bankAccounts: [BankAccount]
}

type BankAccount {
    _id: ObjectID
    owners: [ObjectID]
    type: [String]
    interestRate: Int
    transactions: [Transaction]
    
}

type AccessToken {

}

type Property {

}

type Organisation {

}
```
