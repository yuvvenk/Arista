<!--
  ~ Copyright (c) 2024 Arista Networks, Inc.
  ~ Use of this source code is governed by the Apache License 2.0
  ~ that can be found in the LICENSE file.
  -->
=== "Table"

    | Variable | Type | Required | Default | Value Restrictions | Description |
    | -------- | ---- | -------- | ------- | ------------------ | ----------- |
    | [<samp>router_isis</samp>](## "router_isis") | Dictionary |  |  |  |  |
    | [<samp>&nbsp;&nbsp;instance</samp>](## "router_isis.instance") | String | Required |  |  | ISIS Instance Name |
    | [<samp>&nbsp;&nbsp;net</samp>](## "router_isis.net") | String |  |  |  | CLNS Address like "49.0001.0001.0000.0001.00" |
    | [<samp>&nbsp;&nbsp;router_id</samp>](## "router_isis.router_id") | String |  |  |  | IPv4 Address |
    | [<samp>&nbsp;&nbsp;is_type</samp>](## "router_isis.is_type") | String |  |  | Valid Values:<br>- <code>level-1</code><br>- <code>level-1-2</code><br>- <code>level-2</code> |  |
    | [<samp>&nbsp;&nbsp;log_adjacency_changes</samp>](## "router_isis.log_adjacency_changes") | Boolean |  |  |  |  |
    | [<samp>&nbsp;&nbsp;mpls_ldp_sync_default</samp>](## "router_isis.mpls_ldp_sync_default") | Boolean |  |  |  |  |
    | [<samp>&nbsp;&nbsp;timers</samp>](## "router_isis.timers") | Dictionary |  |  |  |  |
    | [<samp>&nbsp;&nbsp;&nbsp;&nbsp;local_convergence</samp>](## "router_isis.timers.local_convergence") | Dictionary |  |  |  |  |
    | [<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;protected_prefixes</samp>](## "router_isis.timers.local_convergence.protected_prefixes") | Boolean |  |  |  |  |
    | [<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;delay</samp>](## "router_isis.timers.local_convergence.delay") | Integer |  | `10000` |  | Delay in milliseconds. |
    | [<samp>&nbsp;&nbsp;set_overload_bit</samp>](## "router_isis.set_overload_bit") | Dictionary |  |  |  |  |
    | [<samp>&nbsp;&nbsp;&nbsp;&nbsp;enabled</samp>](## "router_isis.set_overload_bit.enabled") | Boolean |  |  |  |  |
    | [<samp>&nbsp;&nbsp;&nbsp;&nbsp;on_startup</samp>](## "router_isis.set_overload_bit.on_startup") | Dictionary |  |  |  |  |
    | [<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;delay</samp>](## "router_isis.set_overload_bit.on_startup.delay") | Integer |  |  |  | Number of seconds. |
    | [<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;wait_for_bgp</samp>](## "router_isis.set_overload_bit.on_startup.wait_for_bgp") | Dictionary |  |  |  |  |
    | [<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;enabled</samp>](## "router_isis.set_overload_bit.on_startup.wait_for_bgp.enabled") | Boolean |  |  |  |  |
    | [<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;timeout</samp>](## "router_isis.set_overload_bit.on_startup.wait_for_bgp.timeout") | Integer |  |  |  | Number of seconds. |
    | [<samp>&nbsp;&nbsp;authentication</samp>](## "router_isis.authentication") | Dictionary |  |  |  |  |
    | [<samp>&nbsp;&nbsp;&nbsp;&nbsp;both</samp>](## "router_isis.authentication.both") | Dictionary |  |  |  | Authentication settings for level-1 and level-2. 'both' takes precedence over 'level_1' and 'level_2' settings. |
    | [<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;key_type</samp>](## "router_isis.authentication.both.key_type") | String |  |  | Valid Values:<br>- <code>0</code><br>- <code>7</code><br>- <code>8a</code> | Configure authentication key type. Default key_id is 0. |
    | [<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;key</samp>](## "router_isis.authentication.both.key") | String |  |  |  | Password string. |
    | [<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;key_ids</samp>](## "router_isis.authentication.both.key_ids") | List, items: Dictionary |  |  |  |  |
    | [<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;id</samp>](## "router_isis.authentication.both.key_ids.[].id") | Integer | Required, Unique |  | Min: 1<br>Max: 65535 | Configure authentication key-id. |
    | [<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;algorithm</samp>](## "router_isis.authentication.both.key_ids.[].algorithm") | String | Required |  | Valid Values:<br>- <code>sha-1</code><br>- <code>sha-224</code><br>- <code>sha-256</code><br>- <code>sha-384</code><br>- <code>sha-512</code> |  |
    | [<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;key_type</samp>](## "router_isis.authentication.both.key_ids.[].key_type") | String | Required |  | Valid Values:<br>- <code>0</code><br>- <code>7</code><br>- <code>8a</code> | Configure authentication key type. |
    | [<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;key</samp>](## "router_isis.authentication.both.key_ids.[].key") | String | Required |  |  | Password string. |
    | [<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;rfc_5310</samp>](## "router_isis.authentication.both.key_ids.[].rfc_5310") | Boolean |  |  |  | SHA digest computation according to rfc5310. |
    | [<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;mode</samp>](## "router_isis.authentication.both.mode") | String |  |  | Valid Values:<br>- <code>md5</code><br>- <code>sha</code><br>- <code>text</code><br>- <code>shared_secret</code> | Authentication mode. |
    | [<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;sha</samp>](## "router_isis.authentication.both.sha") | Dictionary |  |  |  | Required settings for authentication mode 'sha'. |
    | [<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;key_id</samp>](## "router_isis.authentication.both.sha.key_id") | Integer | Required |  | Min: 1<br>Max: 65535 |  |
    | [<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;shared_secret</samp>](## "router_isis.authentication.both.shared_secret") | Dictionary |  |  |  | Required settings for authentication mode 'shared_secret'. |
    | [<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;profile</samp>](## "router_isis.authentication.both.shared_secret.profile") | String | Required |  |  |  |
    | [<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;algorithm</samp>](## "router_isis.authentication.both.shared_secret.algorithm") | String | Required |  | Valid Values:<br>- <code>md5</code><br>- <code>sha-1</code><br>- <code>sha-224</code><br>- <code>sha-256</code><br>- <code>sha-384</code><br>- <code>sha-512</code> |  |
    | [<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;rx_disabled</samp>](## "router_isis.authentication.both.rx_disabled") | Boolean |  |  |  |  |
    | [<samp>&nbsp;&nbsp;&nbsp;&nbsp;level_1</samp>](## "router_isis.authentication.level_1") | Dictionary |  |  |  | Authentication settings for level-1. 'both' takes precedence over 'level_1' and 'level_2' settings. |
    | [<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;key_type</samp>](## "router_isis.authentication.level_1.key_type") | String |  |  | Valid Values:<br>- <code>0</code><br>- <code>7</code><br>- <code>8a</code> | Configure authentication key type. Default key_id is 0. |
    | [<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;key</samp>](## "router_isis.authentication.level_1.key") | String |  |  |  | Password string. |
    | [<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;key_ids</samp>](## "router_isis.authentication.level_1.key_ids") | List, items: Dictionary |  |  |  |  |
    | [<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;id</samp>](## "router_isis.authentication.level_1.key_ids.[].id") | Integer | Required, Unique |  | Min: 1<br>Max: 65535 | Configure authentication key-id. |
    | [<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;algorithm</samp>](## "router_isis.authentication.level_1.key_ids.[].algorithm") | String | Required |  | Valid Values:<br>- <code>sha-1</code><br>- <code>sha-224</code><br>- <code>sha-256</code><br>- <code>sha-384</code><br>- <code>sha-512</code> |  |
    | [<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;key_type</samp>](## "router_isis.authentication.level_1.key_ids.[].key_type") | String | Required |  | Valid Values:<br>- <code>0</code><br>- <code>7</code><br>- <code>8a</code> | Configure authentication key type. |
    | [<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;key</samp>](## "router_isis.authentication.level_1.key_ids.[].key") | String | Required |  |  | Password string. |
    | [<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;rfc_5310</samp>](## "router_isis.authentication.level_1.key_ids.[].rfc_5310") | Boolean |  |  |  | SHA digest computation according to rfc5310. |
    | [<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;mode</samp>](## "router_isis.authentication.level_1.mode") | String |  |  | Valid Values:<br>- <code>md5</code><br>- <code>sha</code><br>- <code>text</code><br>- <code>shared_secret</code> | Authentication mode. |
    | [<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;sha</samp>](## "router_isis.authentication.level_1.sha") | Dictionary |  |  |  | Required settings for authentication mode 'sha'. |
    | [<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;key_id</samp>](## "router_isis.authentication.level_1.sha.key_id") | Integer | Required |  | Min: 1<br>Max: 65535 |  |
    | [<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;shared_secret</samp>](## "router_isis.authentication.level_1.shared_secret") | Dictionary |  |  |  | Required settings for authentication mode 'shared_secret'. |
    | [<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;profile</samp>](## "router_isis.authentication.level_1.shared_secret.profile") | String | Required |  |  |  |
    | [<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;algorithm</samp>](## "router_isis.authentication.level_1.shared_secret.algorithm") | String | Required |  | Valid Values:<br>- <code>md5</code><br>- <code>sha-1</code><br>- <code>sha-224</code><br>- <code>sha-256</code><br>- <code>sha-384</code><br>- <code>sha-512</code> |  |
    | [<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;rx_disabled</samp>](## "router_isis.authentication.level_1.rx_disabled") | Boolean |  |  |  |  |
    | [<samp>&nbsp;&nbsp;&nbsp;&nbsp;level_2</samp>](## "router_isis.authentication.level_2") | Dictionary |  |  |  | Authentication settings for level-2. 'both' takes precedence over 'level_1' and 'level_2' settings. |
    | [<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;key_type</samp>](## "router_isis.authentication.level_2.key_type") | String |  |  | Valid Values:<br>- <code>0</code><br>- <code>7</code><br>- <code>8a</code> | Configure authentication key type. Default key_id is 0. |
    | [<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;key</samp>](## "router_isis.authentication.level_2.key") | String |  |  |  | Password string. |
    | [<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;key_ids</samp>](## "router_isis.authentication.level_2.key_ids") | List, items: Dictionary |  |  |  |  |
    | [<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;id</samp>](## "router_isis.authentication.level_2.key_ids.[].id") | Integer | Required, Unique |  | Min: 1<br>Max: 65535 | Configure authentication key-id. |
    | [<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;algorithm</samp>](## "router_isis.authentication.level_2.key_ids.[].algorithm") | String | Required |  | Valid Values:<br>- <code>sha-1</code><br>- <code>sha-224</code><br>- <code>sha-256</code><br>- <code>sha-384</code><br>- <code>sha-512</code> |  |
    | [<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;key_type</samp>](## "router_isis.authentication.level_2.key_ids.[].key_type") | String | Required |  | Valid Values:<br>- <code>0</code><br>- <code>7</code><br>- <code>8a</code> | Configure authentication key type. |
    | [<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;key</samp>](## "router_isis.authentication.level_2.key_ids.[].key") | String | Required |  |  | Password string. |
    | [<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;rfc_5310</samp>](## "router_isis.authentication.level_2.key_ids.[].rfc_5310") | Boolean |  |  |  | SHA digest computation according to rfc5310. |
    | [<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;mode</samp>](## "router_isis.authentication.level_2.mode") | String |  |  | Valid Values:<br>- <code>md5</code><br>- <code>sha</code><br>- <code>text</code><br>- <code>shared_secret</code> | Authentication mode. |
    | [<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;sha</samp>](## "router_isis.authentication.level_2.sha") | Dictionary |  |  |  | Required settings for authentication mode 'sha'. |
    | [<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;key_id</samp>](## "router_isis.authentication.level_2.sha.key_id") | Integer | Required |  | Min: 1<br>Max: 65535 |  |
    | [<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;shared_secret</samp>](## "router_isis.authentication.level_2.shared_secret") | Dictionary |  |  |  | Required settings for authentication mode 'shared_secret'. |
    | [<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;profile</samp>](## "router_isis.authentication.level_2.shared_secret.profile") | String | Required |  |  |  |
    | [<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;algorithm</samp>](## "router_isis.authentication.level_2.shared_secret.algorithm") | String | Required |  | Valid Values:<br>- <code>md5</code><br>- <code>sha-1</code><br>- <code>sha-224</code><br>- <code>sha-256</code><br>- <code>sha-384</code><br>- <code>sha-512</code> |  |
    | [<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;rx_disabled</samp>](## "router_isis.authentication.level_2.rx_disabled") | Boolean |  |  |  |  |
    | [<samp>&nbsp;&nbsp;advertise</samp>](## "router_isis.advertise") | Dictionary |  |  |  |  |
    | [<samp>&nbsp;&nbsp;&nbsp;&nbsp;passive_only</samp>](## "router_isis.advertise.passive_only") | Boolean |  |  |  |  |
    | [<samp>&nbsp;&nbsp;address_family</samp>](## "router_isis.address_family") | List, items: String |  |  |  |  |
    | [<samp>&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;&lt;str&gt;</samp>](## "router_isis.address_family.[]") <span style="color:red">deprecated</span> | String |  |  | Valid Values:<br>- <code>ipv4</code><br>- <code>ipv6</code><br>- <code>ipv4 unicast</code><br>- <code>ipv6 unicast</code> | Address Family<span style="color:red">This key is deprecated. Support will be removed in AVD version 5.0.0. Use <samp>address_family_ipv4.enabled or address_family_ipv6.enabled</samp> instead.</span> |
    | [<samp>&nbsp;&nbsp;isis_af_defaults</samp>](## "router_isis.isis_af_defaults") | List, items: String |  |  |  |  |
    | [<samp>&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;&lt;str&gt;</samp>](## "router_isis.isis_af_defaults.[]") <span style="color:red">deprecated</span> | String |  |  |  | EOS CLI rendered under the address families<br>Example "maximum-paths 64"<br><span style="color:red">This key is deprecated. Support will be removed in AVD version 5.0.0. Use <samp>address_family_ipv4/address_family_ipv6</samp> instead.</span> |
    | [<samp>&nbsp;&nbsp;redistribute_routes</samp>](## "router_isis.redistribute_routes") | List, items: Dictionary |  |  |  |  |
    | [<samp>&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;source_protocol</samp>](## "router_isis.redistribute_routes.[].source_protocol") | String | Required |  | Valid Values:<br>- <code>bgp</code><br>- <code>connected</code><br>- <code>isis</code><br>- <code>ospf</code><br>- <code>ospfv3</code><br>- <code>static</code> |  |
    | [<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;route_map</samp>](## "router_isis.redistribute_routes.[].route_map") | String |  |  |  | Route-map name |
    | [<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;include_leaked</samp>](## "router_isis.redistribute_routes.[].include_leaked") | Boolean |  |  |  |  |
    | [<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;ospf_route_type</samp>](## "router_isis.redistribute_routes.[].ospf_route_type") | String |  |  | Valid Values:<br>- <code>external</code><br>- <code>internal</code><br>- <code>nssa-external</code> | ospf_route_type is required with source_protocols 'ospf' and 'ospfv3' |
    | [<samp>&nbsp;&nbsp;address_family_ipv4</samp>](## "router_isis.address_family_ipv4") | Dictionary |  |  |  |  |
    | [<samp>&nbsp;&nbsp;&nbsp;&nbsp;enabled</samp>](## "router_isis.address_family_ipv4.enabled") | Boolean |  |  |  |  |
    | [<samp>&nbsp;&nbsp;&nbsp;&nbsp;maximum_paths</samp>](## "router_isis.address_family_ipv4.maximum_paths") | Integer |  |  | Min: 1<br>Max: 128 |  |
    | [<samp>&nbsp;&nbsp;&nbsp;&nbsp;bfd_all_interfaces</samp>](## "router_isis.address_family_ipv4.bfd_all_interfaces") | Boolean |  |  |  | Enable BFD on all interfaces. |
    | [<samp>&nbsp;&nbsp;&nbsp;&nbsp;fast_reroute_ti_lfa</samp>](## "router_isis.address_family_ipv4.fast_reroute_ti_lfa") | Dictionary |  |  |  |  |
    | [<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;mode</samp>](## "router_isis.address_family_ipv4.fast_reroute_ti_lfa.mode") | String |  |  | Valid Values:<br>- <code>link-protection</code><br>- <code>node-protection</code> |  |
    | [<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;level</samp>](## "router_isis.address_family_ipv4.fast_reroute_ti_lfa.level") | String |  |  | Valid Values:<br>- <code>level-1</code><br>- <code>level-2</code> |  |
    | [<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;srlg</samp>](## "router_isis.address_family_ipv4.fast_reroute_ti_lfa.srlg") | Dictionary |  |  |  | Shared Risk Link Group |
    | [<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;enable</samp>](## "router_isis.address_family_ipv4.fast_reroute_ti_lfa.srlg.enable") | Boolean |  |  |  |  |
    | [<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;strict</samp>](## "router_isis.address_family_ipv4.fast_reroute_ti_lfa.srlg.strict") | Boolean |  |  |  |  |
    | [<samp>&nbsp;&nbsp;&nbsp;&nbsp;tunnel_source_labeled_unicast</samp>](## "router_isis.address_family_ipv4.tunnel_source_labeled_unicast") | Dictionary |  |  |  |  |
    | [<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;enabled</samp>](## "router_isis.address_family_ipv4.tunnel_source_labeled_unicast.enabled") | Boolean |  |  |  |  |
    | [<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;rcf</samp>](## "router_isis.address_family_ipv4.tunnel_source_labeled_unicast.rcf") | String |  |  |  | Route Control Function |
    | [<samp>&nbsp;&nbsp;address_family_ipv6</samp>](## "router_isis.address_family_ipv6") | Dictionary |  |  |  |  |
    | [<samp>&nbsp;&nbsp;&nbsp;&nbsp;enabled</samp>](## "router_isis.address_family_ipv6.enabled") | Boolean |  |  |  |  |
    | [<samp>&nbsp;&nbsp;&nbsp;&nbsp;maximum_paths</samp>](## "router_isis.address_family_ipv6.maximum_paths") | Integer |  |  | Min: 1<br>Max: 128 |  |
    | [<samp>&nbsp;&nbsp;&nbsp;&nbsp;bfd_all_interfaces</samp>](## "router_isis.address_family_ipv6.bfd_all_interfaces") | Boolean |  |  |  | Enable BFD on all interfaces. |
    | [<samp>&nbsp;&nbsp;&nbsp;&nbsp;fast_reroute_ti_lfa</samp>](## "router_isis.address_family_ipv6.fast_reroute_ti_lfa") | Dictionary |  |  |  |  |
    | [<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;mode</samp>](## "router_isis.address_family_ipv6.fast_reroute_ti_lfa.mode") | String |  |  | Valid Values:<br>- <code>link-protection</code><br>- <code>node-protection</code> |  |
    | [<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;level</samp>](## "router_isis.address_family_ipv6.fast_reroute_ti_lfa.level") | String |  |  | Valid Values:<br>- <code>level-1</code><br>- <code>level-2</code> | Optional, default is to protect all levels. |
    | [<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;srlg</samp>](## "router_isis.address_family_ipv6.fast_reroute_ti_lfa.srlg") | Dictionary |  |  |  | Shared Risk Link Group |
    | [<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;enable</samp>](## "router_isis.address_family_ipv6.fast_reroute_ti_lfa.srlg.enable") | Boolean |  |  |  |  |
    | [<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;strict</samp>](## "router_isis.address_family_ipv6.fast_reroute_ti_lfa.srlg.strict") | Boolean |  |  |  |  |
    | [<samp>&nbsp;&nbsp;segment_routing_mpls</samp>](## "router_isis.segment_routing_mpls") | Dictionary |  |  |  |  |
    | [<samp>&nbsp;&nbsp;&nbsp;&nbsp;enabled</samp>](## "router_isis.segment_routing_mpls.enabled") | Boolean |  |  |  |  |
    | [<samp>&nbsp;&nbsp;&nbsp;&nbsp;router_id</samp>](## "router_isis.segment_routing_mpls.router_id") | String |  |  |  |  |
    | [<samp>&nbsp;&nbsp;&nbsp;&nbsp;prefix_segments</samp>](## "router_isis.segment_routing_mpls.prefix_segments") | List, items: Dictionary |  |  |  |  |
    | [<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;prefix</samp>](## "router_isis.segment_routing_mpls.prefix_segments.[].prefix") | String |  |  |  |  |
    | [<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;index</samp>](## "router_isis.segment_routing_mpls.prefix_segments.[].index") | Integer |  |  |  |  |
    | [<samp>&nbsp;&nbsp;spf_interval</samp>](## "router_isis.spf_interval") | Dictionary |  |  |  |  |
    | [<samp>&nbsp;&nbsp;&nbsp;&nbsp;interval</samp>](## "router_isis.spf_interval.interval") | Integer |  |  | Min: 1<br>Max: 300 | Maximum interval between two SPFs in seconds. |
    | [<samp>&nbsp;&nbsp;&nbsp;&nbsp;wait_interval</samp>](## "router_isis.spf_interval.wait_interval") | Integer |  |  | Min: 1<br>Max: 300000 | Initial wait interval for SPF in milliseconds. |
    | [<samp>&nbsp;&nbsp;graceful_restart</samp>](## "router_isis.graceful_restart") | Dictionary |  |  |  |  |
    | [<samp>&nbsp;&nbsp;&nbsp;&nbsp;enabled</samp>](## "router_isis.graceful_restart.enabled") | Boolean |  |  |  |  |
    | [<samp>&nbsp;&nbsp;&nbsp;&nbsp;restart_hold_time</samp>](## "router_isis.graceful_restart.restart_hold_time") | Integer |  |  | Min: 5<br>Max: 300 | Number of seconds. |
    | [<samp>&nbsp;&nbsp;&nbsp;&nbsp;t2</samp>](## "router_isis.graceful_restart.t2") | Dictionary |  |  |  |  |
    | [<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;level_1_wait_time</samp>](## "router_isis.graceful_restart.t2.level_1_wait_time") | Integer |  |  | Min: 5<br>Max: 300 | Level-1 LSP database sync wait time in seconds. |
    | [<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;level_2_wait_time</samp>](## "router_isis.graceful_restart.t2.level_2_wait_time") | Integer |  |  | Min: 5<br>Max: 300 | Level-2 LSP database sync wait time in seconds. |
    | [<samp>&nbsp;&nbsp;eos_cli</samp>](## "router_isis.eos_cli") | String |  |  |  | Multiline EOS CLI rendered directly on the router isis in the final EOS configuration. |

=== "YAML"

    ```yaml
    router_isis:

      # ISIS Instance Name
      instance: <str; required>

      # CLNS Address like "49.0001.0001.0000.0001.00"
      net: <str>

      # IPv4 Address
      router_id: <str>
      is_type: <str; "level-1" | "level-1-2" | "level-2">
      log_adjacency_changes: <bool>
      mpls_ldp_sync_default: <bool>
      timers:
        local_convergence:
          protected_prefixes: <bool>

          # Delay in milliseconds.
          delay: <int; default=10000>
      set_overload_bit:
        enabled: <bool>
        on_startup:

          # Number of seconds.
          delay: <int>
          wait_for_bgp:
            enabled: <bool>

            # Number of seconds.
            timeout: <int>
      authentication:

        # Authentication settings for level-1 and level-2. 'both' takes precedence over 'level_1' and 'level_2' settings.
        both:

          # Configure authentication key type. Default key_id is 0.
          key_type: <str; "0" | "7" | "8a">

          # Password string.
          key: <str>
          key_ids:

              # Configure authentication key-id.
            - id: <int; 1-65535; required; unique>
              algorithm: <str; "sha-1" | "sha-224" | "sha-256" | "sha-384" | "sha-512"; required>

              # Configure authentication key type.
              key_type: <str; "0" | "7" | "8a"; required>

              # Password string.
              key: <str; required>

              # SHA digest computation according to rfc5310.
              rfc_5310: <bool>

          # Authentication mode.
          mode: <str; "md5" | "sha" | "text" | "shared_secret">

          # Required settings for authentication mode 'sha'.
          sha:
            key_id: <int; 1-65535; required>

          # Required settings for authentication mode 'shared_secret'.
          shared_secret:
            profile: <str; required>
            algorithm: <str; "md5" | "sha-1" | "sha-224" | "sha-256" | "sha-384" | "sha-512"; required>
          rx_disabled: <bool>

        # Authentication settings for level-1. 'both' takes precedence over 'level_1' and 'level_2' settings.
        level_1:

          # Configure authentication key type. Default key_id is 0.
          key_type: <str; "0" | "7" | "8a">

          # Password string.
          key: <str>
          key_ids:

              # Configure authentication key-id.
            - id: <int; 1-65535; required; unique>
              algorithm: <str; "sha-1" | "sha-224" | "sha-256" | "sha-384" | "sha-512"; required>

              # Configure authentication key type.
              key_type: <str; "0" | "7" | "8a"; required>

              # Password string.
              key: <str; required>

              # SHA digest computation according to rfc5310.
              rfc_5310: <bool>

          # Authentication mode.
          mode: <str; "md5" | "sha" | "text" | "shared_secret">

          # Required settings for authentication mode 'sha'.
          sha:
            key_id: <int; 1-65535; required>

          # Required settings for authentication mode 'shared_secret'.
          shared_secret:
            profile: <str; required>
            algorithm: <str; "md5" | "sha-1" | "sha-224" | "sha-256" | "sha-384" | "sha-512"; required>
          rx_disabled: <bool>

        # Authentication settings for level-2. 'both' takes precedence over 'level_1' and 'level_2' settings.
        level_2:

          # Configure authentication key type. Default key_id is 0.
          key_type: <str; "0" | "7" | "8a">

          # Password string.
          key: <str>
          key_ids:

              # Configure authentication key-id.
            - id: <int; 1-65535; required; unique>
              algorithm: <str; "sha-1" | "sha-224" | "sha-256" | "sha-384" | "sha-512"; required>

              # Configure authentication key type.
              key_type: <str; "0" | "7" | "8a"; required>

              # Password string.
              key: <str; required>

              # SHA digest computation according to rfc5310.
              rfc_5310: <bool>

          # Authentication mode.
          mode: <str; "md5" | "sha" | "text" | "shared_secret">

          # Required settings for authentication mode 'sha'.
          sha:
            key_id: <int; 1-65535; required>

          # Required settings for authentication mode 'shared_secret'.
          shared_secret:
            profile: <str; required>
            algorithm: <str; "md5" | "sha-1" | "sha-224" | "sha-256" | "sha-384" | "sha-512"; required>
          rx_disabled: <bool>
      advertise:
        passive_only: <bool>
      address_family:

          # Address Family
          # This key is deprecated.
          # Support will be removed in AVD version 5.0.0.
          # Use <samp>address_family_ipv4.enabled or address_family_ipv6.enabled</samp> instead.
        - <str; "ipv4" | "ipv6" | "ipv4 unicast" | "ipv6 unicast">
      isis_af_defaults:

          # EOS CLI rendered under the address families
          # Example "maximum-paths 64"
          # This key is deprecated.
          # Support will be removed in AVD version 5.0.0.
          # Use <samp>address_family_ipv4/address_family_ipv6</samp> instead.
        - <str>
      redistribute_routes:
        - source_protocol: <str; "bgp" | "connected" | "isis" | "ospf" | "ospfv3" | "static"; required>

          # Route-map name
          route_map: <str>
          include_leaked: <bool>

          # ospf_route_type is required with source_protocols 'ospf' and 'ospfv3'
          ospf_route_type: <str; "external" | "internal" | "nssa-external">
      address_family_ipv4:
        enabled: <bool>
        maximum_paths: <int; 1-128>

        # Enable BFD on all interfaces.
        bfd_all_interfaces: <bool>
        fast_reroute_ti_lfa:
          mode: <str; "link-protection" | "node-protection">
          level: <str; "level-1" | "level-2">

          # Shared Risk Link Group
          srlg:
            enable: <bool>
            strict: <bool>
        tunnel_source_labeled_unicast:
          enabled: <bool>

          # Route Control Function
          rcf: <str>
      address_family_ipv6:
        enabled: <bool>
        maximum_paths: <int; 1-128>

        # Enable BFD on all interfaces.
        bfd_all_interfaces: <bool>
        fast_reroute_ti_lfa:
          mode: <str; "link-protection" | "node-protection">

          # Optional, default is to protect all levels.
          level: <str; "level-1" | "level-2">

          # Shared Risk Link Group
          srlg:
            enable: <bool>
            strict: <bool>
      segment_routing_mpls:
        enabled: <bool>
        router_id: <str>
        prefix_segments:
          - prefix: <str>
            index: <int>
      spf_interval:

        # Maximum interval between two SPFs in seconds.
        interval: <int; 1-300>

        # Initial wait interval for SPF in milliseconds.
        wait_interval: <int; 1-300000>
      graceful_restart:
        enabled: <bool>

        # Number of seconds.
        restart_hold_time: <int; 5-300>
        t2:

          # Level-1 LSP database sync wait time in seconds.
          level_1_wait_time: <int; 5-300>

          # Level-2 LSP database sync wait time in seconds.
          level_2_wait_time: <int; 5-300>

      # Multiline EOS CLI rendered directly on the router isis in the final EOS configuration.
      eos_cli: <str>
    ```
