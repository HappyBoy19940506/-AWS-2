            1.  EACH region has only a VPC      
            
            2.  VPC has -- name.
                        -- CIDR 26-64 SPOTS. 28-16 SPOTS
                        e.g. divided in 4 blocks-   0.0.0.0/28 - from 0.0.0.0 to 0.0.0.15
                                                    0.0.0.16/28  - from 0.0.0.16 to 0.0.0.31
                                                    0.0.0.32/28  - from 0.0.0.32 to 0.0.0.47
                                                    0.0.0.48/28 - from 0.0.0.48 to 0.0.0.63
                        -- in each block, first 4 ip and the last ip are reserved, so there are 16-5 = 11 IPs available when set down
                        -- Tenancy - dedicated( can only launch dedicated instances or dedicated host instances)
                                    if choose default，  u can launch all three types of instances
                                    
            3. Subnets
                        SUBNETS are based on the availability zone. 
                        EACH SUBNET in One AZ
                        ONE VPC -- ONE region - TWO OR MORE AZ -  MORE Subnets
                        Many Subnets can be in one availability zone,
                        
                        Public subnets in a specific AZ   
                        Private Subnets in specific AZ 
                        
             4. Route Table
                        One VPC can have serveral route table
                        But one route table can only in one VPC
                        A route table can associate with serveral subnets. 
                        E.g.  A public route table can associate all public subnets in all AZs in one VPC in one region.
                        
                        One Subnet can only match only one Route table.
                        But a route table can associate with many subnets.
                        
                        
                        Public Route Table --- Connect to a Internet Gateway.
                        Routes :  0.0.0.0/0 -- IGW
                        
             5. Internet Gateway
                  A Region - A VPC- A Internet Gateway
                  No need to configure, auto set wel
                  
             6. NAT Gateway
                        
                  1. Create a NAT GATEWAY in a *public subnet* , and it will occupy one IP address.
                  
                  2. Choose an ELP ip address to it.
                  
                  3. Go to the private Route tabe--
                     Connect to a NAT Gateway
                     Routes : 0.0.0.0/0 -- NAT GATEWAY
                        
                        
                        
                        
