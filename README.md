# csr1000v-rest-api-ansible

Playbooks for network automation of CSR1000v through REST API using Ansible.
Designed to use in Ansible AWX/Tower, but also possible to use in a plain/command line based Ansible.

## Variables documentation

### Basic connection

| **Variables**               | Description                  | Example |
| --------------------------- | ---------------------------- | ---- |
| **var_device_host** | IP address / host name (specified either in AWX/Tower or having its own FQDN) | "cisco-1", or "192.168.122.141", or "distribution.gateway.bakmie.me" |
| **var_device_protocol**     | Specifies the protocol used to control the device.(Only for devices controlled with REST API, *or maybe not implemented, haha*) | "https", "http" |
| **var_device_user** | Specifies the username used to connect with the device. (Only for devices controlled with REST API) | "username" |
| **var_device_pass** | Specifies the password used to connect with the device. (Only for devices controlled with REST API) | "password" |
|  |  |  |

### Interface configuration

| **Variables**               | Description                  | Example |
| --------------------------- | ---------------------------- | ---- |
| **var_set_interface_type**  | Specifies the desired interface type of the chosen interface to configure. Available only for devices with REST API (VyOS, IOS XE). | "ethernet", "dummy" |
| **var_set_interface**       | Specifies the desired interface to be configured. Interface naming varies between each device. | "gigabitEthernet1", "Fa0/1", "eth0" |
| **var_set_ip_addr**         | Assigns the desired IP address to be configured into an interface. | "192.168.1.1" |
| **var_set_netmask**         | Specifies the subnet mask of the desired IP address to be configured. Different devices has its own format. | "255.255.255.0" for Cisco devices, "/24" for MikroTik or Vyatta VyOS devices. |


### Static Routing

| **Variables**               | Description                  | Example |
| --------------------------- | ---------------------------- | ---- |
| **var_set_route_1**       |                              |      |
| **var_set_route_1_netmask** |                              |      |
| **var_set_route_2**         |                              |      |


### Custom command line

| **Variables**               | Description                  | Example |
| --------------------------- | ---------------------------- | ---- |
| **var_custom_command**      | This variable is used to contain customized command lines to be executed directly into the device. The format should be in the list (JSON dictionary in AWX/Tower REST API). |      |


### Output handling
| **Variables**               | Description                  | Example |
| --------------------------- | ---------------------------- | ---- |
| **var_output_task**      | This variable is used to contain outputs from the finished task execution. |      |
| **var_output_task_lines**      | This variable is used to contain outputs from the finished task execution. (in list of output lines format) |      |
