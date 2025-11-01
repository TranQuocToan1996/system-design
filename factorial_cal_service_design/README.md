- Requiments: Design a system for calculate the factorial numbers

- Clarify requiments: 
+ Maxium of the factorial: Try as big as possible in condition of conditions of our servers.
+ Request calculte for the small side of factorial more than big side.
+ No need to return the result right away.
+ Technical requiments: Durable, high availability, can retry.
+ R/W ratio ~1000

- Current implementation:
+ Only 1 Step function calculate from bottom to up
+ Redis cluster RLU cache eviction, TTL
+ Lazy calculate by compare the max_request_number and currently_calculate_done_number
+ DB read replica (Connection Proxy AWS)
+ Assume the authenticate, authorization ok now.



- Further improve:
+ Cache preloading for small number Redis
+ Compression in lambda function after upload to S3
+ CDN for s3 result files
+ Use distributed computing framework like Flink or Spark (Chunk + partial result + storage, tree multiplication)