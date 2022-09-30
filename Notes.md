            1.  EACH region has only a VPC      
            
            2.  VPC has -- name.
                        -- CIDR 26-64 SPOTS. 28-16 SPOTS
                        e.g. divided in 4 blocks-   0.0.0.0/28 - from 0.0.0.0 to 0.0.0.15
                                                    0.0.0.16/28  - from 0.0.0.16 to 0.0.0.31
                                                    0.0.0.32/28  - from 0.0.0.32 to 0.0.0.47
                                                    0.0.0.48/28 - from 0.0.0.48 to 0.0.0.63
                        -- in each block, first 4 ip and the last ip are reserved, so there are 16-5 = 11 IPs available when set down
            3. -- Tenancy - dedicated( can only launch dedicated instances or dedicated host instances)
                                    if choose default，  u can launch all three types of instances
