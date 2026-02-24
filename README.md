# Splunk OT Sandbox

Fake datasets and other helpful bits to develop test OT use cases.

Most base CSVs are 100 rows and may have varying header names to emulate disparate data in a distributed environment.

## Data Dictionary 

### Shared Fields

| **Field Name(s)**  | **Type** | **Description** | **Dataset Mapping(s)** |
| ------------- | ------------- | ------------- | ------------- |
| assigned_staff<br> authorized_user<br> last_user_access<br> operator_signature<br> staff_id<br> user_id | String | Unique employee/tech identifier  | badge_reader_logs.csv (**staff_id**)<br> engineering_ws_edr.csv (**authorized_user**)<br> factory_maintenance_logs.csv(**operator_signature**)<br> jump_host_auth.csv (**user_id**)<br> personnel_security_registry.csv (**staff_id**)<br> safety_system_sis_events.csv (**last_user_access**)<br> work_orders.csv (**assigned_staff**) |
| associated_plc_ip<br> dest_ip<br> endpoint_address<br> ip_v4<br> jump_host_ip<br> malicious_ip<br> observed_ip<br> source_vpn_ip<br> src_ip<br> target_ip<br> target_plc_ip<br> workstation_ip | IPV4 | Various IP address fields | dpi_modbus_logs.csv (**dest_ip, src_ip**)engineering_ws_edr.csv (**target_plc_ip, workstation_ip**)<br> firewall_conduit_logs.csv (**dest_ip, src_ip**)<br> ics_threat_intel_feed(**malicious_ip**)<br> jump_host_auth.csv (**jump_host_ip, source_vpn_ip, target_ip**)<br> network_traffic_topology.csv(**endpoint_address**)<br> safety_system_sis_events.csv (**associated_plc_ip**)<br> tenable_ot_passive_discovery.csv**observed_ip**)<br> wind_factory_telemetry.csv(**ip_v4**)
| asset_tag<br> Component_ID<br> Device_Serial<br> impacted_asset<br> physical_asset_id<br> sensor_id  | String | Hardware identifier  |  asset_security_registry.csv (**Component_ID**)<br> badge_reader_logs.csv(**physical_asset_id**)<br> factory_maintenance_logs.csv (**target_asset_id**)<br> ics_threat_intel_feed.csv(**impacted_asset**)<br> wind_factory_telemetry.csv | 
| ticket_id<br> work_order_ref  | String  | Work permit reference  | factory_maintenance_logs.csv (**work_order_ref**)<br> work_orders.csv (**ticket_id**)|
| cve_id<br> targeted_cve  | String  | Vuln identifier  | ics_threat_intel_feed.csv (**targeted_cve**)<br> tenable_ot_passive_discovery.csv (**cve_id**) |
| mapped_safety_zone<br> Security_Zone_Name<br> safety_zone<br> zone_pair  | String  | Security zone  | firewall_conduit_logs.csv (**zone_pair**)<br> iec_zone_conduit_map.csv (**Security_Zone_Name, mapped_safety_zone**)<br> safety_system_sis_events.csv (**safety_zone**) |
| detected_mac<br> mac_assign  | MAC Address  | Physical hardware address  | network_traffic_topology.csv (**mac_assign**)<br> tenable_ot_passive_discovery.csv(**detected_mac**) |
| timestamp  | Timestamp  | ISO8601  | All datasets (**timestamp**)  |


