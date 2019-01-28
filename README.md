# types

```gql
type User {
    _id: ObjectID
    username: String
    email: String
    phone: String
    name: {
        first: String
        last: String
    }
    profile: {
        eyeColor: String
        dateOfBirth: String
        height: String
        weight: String
        religion: String
        gender: String
        place-of-birth: String
        skinColor: String
        hairColor: String
    }
    addresses: {
        primary: Address
        list: [Address]
    }
    roles: [String]
    cinvir: [{
        type: String
        date: String
    }]
    properties: [Property]
    security: {
        access_tokens: [AccessToken]
    }
    bankAccounts: [BankAccount]
}

type BankAccount {
    _id: ObjectID
    name: String
    settings: {
        daily-limit: Int
    }
    owners: [ObjectID]
    type: [String]
    interestRate: Int
    transactions: [Transaction]
}

type Transaction {

}

type AccessToken {

}

type Property {

}

type Organisation {

}

type CinvirStatus {
    
}
```
