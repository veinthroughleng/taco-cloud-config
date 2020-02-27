# taco-cloud-config

 Many beans are pom-dependency-relative, created just with pom dependency, no need to active profile.
 Such as: RabbitConfig, all controllers, and so on.
 Non-pom-dependency-relative such as:
   MessagingProps in taco-property, beans in taco-model, beans in taco-data.
   
#dev,prod,property,jpa-rest,rest,message,rabbit,rabbit-sender,rabbit-receiver,rabbit-listener,mpa,security

 dev:
   config: log level
 prod:
   config: log level, data source
 eureka:
   config: eureka client config
 property:
   config: properties
 jpa-rest:
   beans: jpa repositories in taco-data,
           IngredientByNameAndTypeConverter in taco-data,
           IngredientAssembler, TacoAssembler in taco-model.
 rest:
   config: rest url,
 message:
   beans: MessagingProps in taco-property.
 jms:
   config: jms config
 jms-sender, jms-receiver, jms-listener
 rabbit:
   config: rabbit config
 rabbit-sender, rabbit-receiver, rabbit-listener
 kafka:
   config: kafka config
 kafka-sender, kafka-listener
 mpa:
    beans: IngredientByIdConverter in taco-data,
 security:
    beans: UserRepository in taco-data.
