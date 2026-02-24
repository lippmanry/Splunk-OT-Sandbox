# Splunk OT Sandbox

Fake datasets and other helpful bits to develop test OT use cases.

Most base CSVs are 100 rows and may have varying header names to emulate disparate data in a distributed environment.

## Data Dictionary 

### Shared Fields

| **Field Name(s)**  | **Type** | **Description** | **Dataset Mapping** |
| ------------- | ------------- | ------------- | ------------- |
| assigned_staff<br> authorized_user<br> last_user_access<br> staff_id<br> user_id | String | Unique employee/tech identifier  | personnel_security_registry.csv (**staff_id**)<br> work_orders.csv (**assigned_staff**)<br> jump_host_auth.csv (**user_id**)<br> engineering_ws_edr.csv (**authorized_user**)<br> badge_reader_logs.csv (**staff_id**)<br> safety_system_sis_events.csv (**last_user_access**) |  
| associated_plc_ip<br> dest_ip<br> ip_v4<br> target_plc_ip  | IPV4 | Target controller IP  | asset_security_registry.csv (**ip_v4**)<br>factory_maintenance_logs.csv (**target_plc_ip**)<br>dpi_modbus_logs.csv (**dest_ip**)<br>engineering_ws_edr.csv (**target_plc_ip**)<br>firewall_conduit_logs.csv (**dest_ip**)<br>safety_system_sis_events.csv (**associated_plc_ip**) |
| source_vpn_ip<br> src_ip<br> workstation_ip  | IPV4 | IP of initiating host  | jump_host_auth.csv (**source_vpn_ip**)<br>engineering_ws_edr.csv (**workstation_ip**)<br>firewall_conduit_logs.csv (**src_ip**)<br>dpi_modbus_logs.csv (**src_ip**) |
| asset_tag<br> Component_ID<br> sensor_id  | String | Hardware identifier  | asset_security_registry.csv (**Component_ID**)<br>factory_maintenance_logs.csv (**asset_tag**)<br>tenable_ot_passive_discovery.csv (**asset_tag**)<br>wind_factory_telemetry.csv (**sensor_id**) |
| ticket_id<br> work_order_ref  | String  | Work permit reference  | work_orders.csv (**ticket_id**)<br>factory_maintenance_logs.csv (**work_order_ref**) |
| cve_id<br> targeted_cve  | String  | Vuln identifier  | tenable_ot_passive_discovery.csv (**cve_id**)<br>ics_threat_intel_feed.csv (**targeted_cve**) |
| safety_zone<br> zone_id<br> zone_name<br> zone_pair  | String  | Security zone  | iec_zone_conduit_map.csv (**zone_name**)<br>firewall_conduit_logs.csv (**zone_pair**)<br>safety_system_sis_events.csv (**safety_zone**) |
| mac_address  | MAC Address  | Physical hardware address  | asset_security_registry.csv (**mac_address**)<br>network_traffic_topology.csv (**mac_address**) |
| timestamp  | Timestamp  | ISO8601  | All datasets (**timestamp**)  |


