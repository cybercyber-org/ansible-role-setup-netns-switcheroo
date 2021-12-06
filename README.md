This role moves the primary interface (passed in as `switcheroo_if`) into a network namespace of the same name. It then sets up routing and port forwarding from that namespace into the root namespace.

See https://cybercyber.org/using-a-network-namespace-as-nat-router-for-a-vps.html for details.

Parameters:

* `switcheroo_if`: Which interface to move into a namespace
* `switcheroo_ip`: Which IP to give the interface (most likely the one it has now?)
* `switcheroo_mask`: Which mask (in `/`-notation) to give the interface (most likely the one it has now?)
* `switcheroo_ip6`: Which IP6 to give the interface (most likely the one it has now + 1?)
* `switcheroo_ip6_inner`: Which IP6 to give the inner interface (most likely the one `switcheroo_if`  had?)
* `switcheroo_mask6`: Which prefix length to give the interface (most likely the one it has now?)
* `switcheroo_routes`: A list of routes that the root-ns should route into the namespace (e.g. `["default", "192.168.1.2/21"]`)
* `switcheroo_routes6`: A list of ipv6 routes that the root-ns should route into the namespace (e.g. `["default"]`)
* `switcheroo_up_routes`: A list of routes to add to the `switcheroo_if` (`{"target": "default", "router": "1.2.3.4"}`)
* `switcheroo_up_routes6`: A list of routes to add to the `switcheroo_if` (`{"target": "default", "router": "2100::"}`)
* `switcheroo_pfd`: A list of port/protocol that the namespace should forward to the root-namespace (e.g. `[{ "proto": "tcp", "port": "22"}]`
* `switcheroo_down_routes`, `switcheroo_down_routes6`: list of prefixes that should be routed "down" from the namespace to the root namespace
