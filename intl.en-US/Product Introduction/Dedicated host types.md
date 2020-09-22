# Dedicated host types

The type of a dedicated host determines the type and number of the ECS instances that you can create on the dedicated host. This topic describes the types and specifications of dedicated hosts.

## Overview

The type of a dedicated host refers to the specifications of the physical server that corresponds to the dedicated host. These specifications include the CPU model, memory size, local storage space, number of CPU cores, number of CPU sockets, and number of vCPUs.

The predefined ECS instances on a dedicated host can be used in the same scenarios as the ECS instances on a shared host. Therefore, you can create ECS instances on a dedicated host whose type is compatible with the type of the ECS instances. For example, you can create all the ECS instances that belong to the **g6, c6, r6, and ic6** instance families on a **general-purpose g6** dedicated host. For more information, see [Instance families](/intl.en-US/Instance/Instance families.md).

Custom instance types allow you to customize the vCPU-to-memory ratio. For example, you can create custom types of ECS instances on a dedicated host whose type is **general overprovisioned type g6s**. You can also modify the number of vCPUs and the memory size.

## Available types

The following table lists the available types of dedicated hosts.

**Note:**

The storage enhanced type g5se is at the trial stage. If you want to use dedicated hosts of this type, [submit a ticket](https://workorder-intl.console.aliyun.com/#/ticket/createIndex).

|Dedicated host type|Supported ECS instance family|Number of CPU sockets|Physical CPU model|Number of CPU cores|Number of vCPUs|Memory size \(GiB\)|Local SSD \(GiB\)[3](#footnote)|Inbound/outbound bandwidth \(Gbit/s\)[4](#network)|Inbound/outbound packet forwarding rate \(10,000 packets per second\)[4](#network)|
|-------------------|-----------------------------|---------------------|------------------|-------------------|---------------|-------------------|-------------------------------|--------------------------------------------------|----------------------------------------------------------------------------------|
|Reliable general type g6t|g6t|2|Intel ® Xeon ® Platinum 8269 \(Cascade Lake\)|52|104 [1](#vCPU)|384|N/A|32|2400|
|Reliable compute type c6t|c6t|2|Intel ® Xeon ® Platinum 8269 \(Cascade Lake\)|52|104 [1](#vCPU)|192|N/A|32|2400|
|Computation overprovisioned type c6s|Custom|2|Intel Xeon Platinum 8269CY \(Cascade Lake\)|52|208 [2](#vCPU-CPU)|180|N/A|25|600|
|General overprovisioned type g6s|Custom|2|Intel Xeon Platinum 8269CY \(Cascade Lake\)|52|312 [2](#vCPU-CPU)|372|N/A|25|600|
|Memory overprovisioned type r6s|Custom|2|Intel Xeon Platinum 8269CY \(Cascade Lake\)|52|416 [2](#vCPU-CPU)|756|N/A|25|600|
|General purpose type g6|-   ic6
-   c6
-   g6
-   r6

|2|Intel Xeon Platinum 8269CY \(Cascade Lake\)|52|104 [1](#vCPU)|384|N/A|25|600|
|Compute optimized type c6|-   ic6
-   c6

|2|Intel Xeon Platinum 8269CY \(Cascade Lake\)|52|104 [1](#vCPU)|192|N/A|25|600|
|Memory optimized type r6|-   ic6
-   c6
-   g6
-   r6

|2|Intel Xeon Platinum 8269CY \(Cascade Lake\)|52|104 [1](#vCPU)|768|N/A|25|600|
|Local SSD type i2|i2|2|Intel Xeon Platinum 8163 \(Skylake\)|48|80 [1](#vCPU)|640|17880|25|550|
|General purpose type g5|g5|2|Intel Xeon Platinum 8163 \(Skylake\)|48|84 [1](#vCPU)|336|N/A|25|550|
|Compute type c5|c5|2|Intel Xeon Platinum 8163 \(Skylake\)|48|86 [1](#vCPU)|172|N/A|25|550|
|Memory type r5|r5|2|Intel Xeon Platinum 8163 \(Skylake\)|48|86 [1](#vCPU)|688|N/A|25|550|
|CPU overprovisioned type v5|v5|2|Intel Xeon Platinum 8163 \(Skylake\)|48|336 [1](#vCPU-CPU)|672|N/A|25|550|
|Storage enhanced type g5se|g5se|2|Intel Xeon Platinum 8163 \(Skylake\)|48|70 [1](#vCPU)|336|N/A|25|550|
|Network enhanced type g5ne|g5ne|2|Intel Xeon Platinum 8163 \(Skylake\)|48|72 [1](#vCPU)|288|N/A|25|2400|

1. Number of vCPUs for non-overprovisioned type = Number of CPU cores × 2 − Number of vCPUs that are reserved by the dedicated host

2. Number of vCPUs for overprovisioned type = \(Number of CPU cores × 2 − Number of vCPUs that are reserved by the dedicated host\) × CPU overprovisioning ratio

3. For more information about local SSDs, see [Local disks](/intl.en-US/Block Storage/Block Storage overview/Local disks.md).

4. The total packet forwarding rate or bandwidth of all the ECS instances types on a dedicated host must be less than that of the dedicated host. For information about the network performance of all the ECS instances, see [Instance families](/intl.en-US/Instance/Instance families.md).

## Retired types

The following table lists the types of dedicated hosts that are retired.

|Dedicated host type|Supported ECS instance family|Number of CPU sockets|Physical CPU model|Number of CPU cores|Number of vCPUs|Memory size \(GiB\)|Local SSD \(GiB\)|Inbound/outbound bandwidth \(Gbit/s\)|Inbound/outbound packet forwarding rate \(10,000 packets per second\)|
|-------------------|-----------------------------|---------------------|------------------|-------------------|---------------|-------------------|-----------------|-------------------------------------|---------------------------------------------------------------------|
|Compute optimized type with enhanced network performance sn1ne|sn1ne|2|Intel Xeon E5-2682 v4 \(Broadwell\)|32|56 [①](#vCPU)|112|N/A|10|450|
|General purpose type with enhanced network performance sn2ne|sn2ne|2|Intel Xeon E5-2682 v4 \(Broadwell\)|32|56 [①](#vCPU)|224|N/A|10|450|
|Memory optimized type with enhanced network performance se1ne|se1ne|2|Intel Xeon E5-2682 v4 \(Broadwell\)|32|56 [①](#vCPU)|480|N/A|10|450|

