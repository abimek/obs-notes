# punishments
#tags
Date: 08-31-2022

Description Here

**External Links:**

## Code Example

```go
provider := CylexPunishmentProvider{}

punishmentRegistry := punishment.New(provider)

punishmentRegistry.addAliases("xuid", "ip", "deviceId")

xBox, err := punishmentRegistry.Xbox("xuid")
if err != nil {
	panic(err)
}
ip, err := punishmentRegistry.Ip("ip")
if err != nil {
	panic(err)
}
if xBox.Banned() {
	(kick)
}
if ip.Banned() {
	(kick)
}
```