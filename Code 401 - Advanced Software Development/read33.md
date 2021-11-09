# GraphQL @connection
> Add relationships between types
> The @connection directive enables you to specify relationships between @model types.

* one-to-one.
* one-to-many.
* and many-to-one.
* > implement many-to-many relationships using two one-to-many connections and a joining @model type.

> Definition

> directive @connection(keyName: String, fields: [String!]  on FIELD_DEFINITION

> @connection specified Relationships between types are annotating fields.

> The keyName argument can optionally be used to specify the name of secondary index that should be queried from the other type in the relationship.

> When specifying a keyName, the fields argument should be provided to indicate which field(s) will be used to get connected objects. If keyName is not provided, then @connection queries the target table's primary index.

`type Project @model {
  id: ID!
  name: String
  teamID: ID!
  team: Team @connection(fields: ["teamID"])
}

type Team @model {
  id: ID!
  name: String!
}`


> The following directives are supported by the AppSync service and can be used within the Amplify GraphQL schemas. These will not be processed by Amplify CLI but passed through to the service as is and will be present in the output schema. For example, Amplify's @auth directive will add these directives under the hood to the output schema.

* @aws_api_key
* @aws_iam
* @aws_oidc
* @aws_cognito_user_pools
* @aws_auth
* @aws_subscribe