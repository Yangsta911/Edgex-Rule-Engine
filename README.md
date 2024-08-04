# Edgex-Rule-Engine
## How to run Edgex Rule Engine
1) Follow the official steps provided https://docs.edgexfoundry.org/3.1/getting-started/native/Ch-BuildRunOnLinuxDistro/ to run all of the edgex services.
2) Replace the export EDGEX__DEFAULT__TOPIC=rules-events line when running ekuiper with export EDGEX__DEFAULT__TOPIC=edgex.rules-events
3) The name of the topic could change and should be found using redis and typing in *psubscribe into the cli and finding all of the readings
4) Run the Virtual Device Service so there is virtual simulated data that the rule engine can read
5) Create an ekuiper stream to read from the edgex message bus using the ./ekuiper executeable or curling the api following the link https://ekuiper.org/docs/en/latest/edgex/edgex_rule_engine_tutorial.html
6) Test that the stream is functioning correctly by using the ./ekuiper executeable and running SELECT * from demo with demo being the name of the stream you have created
7) Create a rule using template https://github.com/lf-edge/ekuiper/blob/master/docs/en_US/edgex/edgex_rule_engine_command.md given here again using the ./ekuiper executeable or the api
8) Query the stream with SELECT * from demo as shown in above link to see that the rule is indeed working and the randomization is set as true
