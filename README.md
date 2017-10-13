# trafgen-cf
A cloudformation template which will launch a trafgen EC2 in VPC to test total raw throughput of your Direct Connect circuit.

## Usage Instructions 
1) Simply launch the Cloudformation stack by clicking here <a href="https://console.aws.amazon.com/cloudformation/home?region=us-east-1#/stacks/new?stackName=trafgen-cf&templateURL=https://s3-us-west-2.amazonaws.com/trafgen-cf/trafgen-cf.json"><img src="https://s3.amazonaws.com/cloudformation-examples/cloudformation-launch-stack.png"/></a>
2) Make sure that you are launching the stack in the correct region
3) Carefully read and fill out all the fields in the form 
4) Choose a single IP that is in a network being advertised to your AWS VPC over DX, and use this as the "target IP" to generate traffic towards. 

The Target IP does NOT have to be assigned to a real device in the remote network. This traffic generator is not expecting a response, and is sending out all UDP traffic.

## WARNING!!
This tool is NOT to be used for any type of malicious purpose. It is only to be used in networks that you own for performance benchmarking. Also, note that it can easily saturate your 1G or 10G Direct Connect circuit. When this happens all other connections may experience high latency and/or packet loss. For this reason it's highly recommended that you schedule a short maintenance window with your company prior to benchmarking.

