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
 dev,prod,eureka,admin,admin-eureka,property,jpa-rest,rest,message,rabbit,rabbit-sender,rabbit-receiver,rabbit-listener,mpa,security,feign-hystrix,jwt

 dev:
   config: log level
   
 prod:
   config: log level, data source
   
 eureka:
   config: eureka client config
   
 property:
   config: properties
   
 jpa-rest:
   beans:  jpa entities in taco-model,
           jpa repositories in taco-data,
           IngredientByNameAndTypeConverter in taco-data,
           IngredientAssembler, TacoAssembler in taco-model.
           
 rest:
   config: rest url,
   beans: IngredientAssembler, TacoAssembler, UserAssembler, OrderAssembler
   
 message:
   config: message config like sources/queues/routing-keys/topics for jms/rabbit/kafka
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
   beans: IngredientByIdConverter in taco-data
   
 security:
   config: security config like oAuth2
   
 feign-hystrix:
   config: feign-hystrix config
   
 eureka:
   config: config for eureka client
 
 admin:
   config: config of which endpoints from actuator/* are exposed for Admin client
 
 admin-eureka:
   config: config for eureka clients to serve their username/password to admin server, who consumes their actuator endpoint
 jwt:
   config: config for jwt(git branch cloud-self-jwt, git tag SECURED_REST_self_jwt)
