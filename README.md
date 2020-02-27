# taco-cloud-config

1. config server/Eureka server
 service-registry(Eureka server) act as a config client, but service-config(config server) doesn't act as a Eureka.

2. configurations
 NOTE:
 Many beans are pom-dependency-relative, created just with pom dependency, no need to active profile.
 Such as: RabbitConfig, all controllers, and so on.
 Non-pom-dependency-relative such as:
   MessagingProps in taco-property, beans in taco-model, beans in taco-data.
   
 ALL configurations:
 dev,prod,property,jpa-rest,rest,message,rabbit,rabbit-sender,rabbit-receiver,rabbit-listener,mpa,security

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
