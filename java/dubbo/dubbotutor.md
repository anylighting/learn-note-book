
#### ArchitecTure

    provider: service provider, register its service to the registry;
    container: initial. load. run the service;
    consumer: invokes services from provider, subscribes from registry;
    registry: component where providers register services and consumers subscribe service;
    monitor: record statistic for services; such as services invoke per minites;

##### Connection

    connections between a provider, aconsumer and a registry are persistent,
    the registry and monitor are optional, consumers can connect to thre service providers
    directly, but will affect ther stability of the whole system;

#### Multicast Registry


#### Load Balanced
    
    Random, round-robin, least-active,  consistent-hash;

#### Fault Tolerance

    fail-over, fail-safe, fail-fast, fail-back, forking;











