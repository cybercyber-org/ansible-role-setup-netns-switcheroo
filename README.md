Parameters:

* `switcheroo_if`: Which interface to move into a namespace
* `switcheroo_ip`: Which IP to give the interface (most likely the one it has now?)
* `switcheroo_mask`: Which mask (in `/`-notation) to give the interface (most likely the one it has now?)
* `switcheroo_ip6`: Which IP6 to give the interface (most likely the one it has now?)
* `switcheroo_mask6`: Which prefix length to give the interface (most likely the one it has now?)
* `switcheroo_routes`: A list of routes that the root-ns should route into the namespace (e.g. `["default", "192.168.1.2/21"]`)
* `switcheroo_pfd`: A list of port/protocol that the namespace should forward to the root-namespace (e.g. `[{ "proto": "tcp", "port": "22"}]`
