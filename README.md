# Wazuh - Decoders

We need to add some decoders to match the events from Resilmesh Framework, go to: https://localhost:4343/app/decoders#/manager/?tab=decoders
and add the following decoders from file [resilmesh_decoders.xml](./resilmesh_decoders.xml) and [resilmesh_ad_decoders.xml](./resilmesh_ad_decoders.xml) one by one, **DO NOT MIX THEM!**

Save it, you can test it too, use the 'Decoders Test' button, and then paste this sample (it has to be in a single line):
```text
2024-10-17T15:06:48.093438+00:00 Vector.ph1_resilmesh_network  {"@timestamp":"2024-08-29T13:27:54.065982398Z","destination":{"ip":"149.171.126.17"},"ecs":{"version":"1.6.0"},"source":{"ip":"175.45.176.3"},"silent_push":{"wazuh_rule_level":9}}
```
if you got a response like the one below, we're done:
```text
**Phase 2: Completed decoding.
	name: 'resilmesh_decoders'
	@timestamp: '2024-08-29T13:27:54.065982398Z'
	destination.ip: '149.171.126.17'
	dstip: '149.171.126.17'
	ecs.version: '1.6.0'
	risk_score: '99'
	source.ip: '175.45.176.3'
	sp_risk_score: '99'
	srcip: '175.45.176.3'

**Phase 3: Completed filtering (rules).
	id: '99901'
	level: '3'
	description: 'Resilmesh'
	groups: '["Resilmesh"]'
	firedtimes: '1'
	mail: 'false'
**Alert to be generated.
```