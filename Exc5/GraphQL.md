# Схема GraphQL для client-info
type Client {
  id: ID!
  name: String!
  age: Int
  documents: [Document] # Список документов клиента
  relatives: [Relative] # Список родственников клиента
}

type Document {
  id: ID!
  type: String!
  number: String!
  issueDate: String
  expiryDate: String
}

type Relative {
  id: ID!
  relationType: String!
  name: String!
  age: Int
}

# Запросы (Queries)
type Query {
  # Получить информацию о клиенте
  client(id: ID!): Client

  # Получить список клиентов по нескольким ID
  clients(ids: [ID!]!): [Client]

  # Получить список документов клиента
  documents(clientId: ID!): [Document]

  # Получить список родственников клиента
  relatives(clientId: ID!): [Relative]
}

