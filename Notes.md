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
                                    
                        -- Choose A VPC  --DNS resolutions true
                                         --DNS hostname true, instances in this VPC will not only get a IP ,but alos a HOSTNAME.
                                    
            3. Subnets
                        SUBNETS are based on the availability zone. 
                        EACH SUBNET in One AZ
                        ONE VPC -- ONE region - TWO OR MORE AZ -  MORE Subnets
                        Many Subnets can be in one availability zone,
                        
                        Public subnets in a specific AZ   -- AUTO ASSIGN IPS - so each time you launch instances, ips will be auto assigned.
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
                     
             7.  NAT GATEWAY VS INTERNET GATEWAY
            Internet Gateway (IGW) allows instances with public IPs to access the internet.
             NAT Gateway (NGW) allows instances with no public IPs to access the internet.
             E.g. your DB level stuff can not have a public IP to connect to the Internet directly, so there should be a proxy things like NAT GATEWAY.
             
             8. NETWORK NACL RULES.
               #NUMBERS -- refers to the rank , it will only respond to the highest rank rules.
               
              ONE VPC === ONE NACL RULES
             
             9. Security Group
             --- INSTANCE LEVEL
             
             10 ELB
             -- handling all the INC Traffic from the Internet, and help distributed into instances into different AZs
             --- health check all the instances
             ---  can put it in the public subnet or private subnet, ( NAT GATEWAY MUST BE PUT IN THE PUBLIC SUBNET)
             --- SHOULD BE ACROSS AZs aka choose more than one subnets. like in the middle of AZs
             
             11 ELB VS NAT
                         INC TRAFFIC DISTRIBUTION -ELB
                         NAT OUTGOING TRAFFIC FROM INSTANCE TO INTERNET -NAT
             
             
                        
                        
                        
                        
