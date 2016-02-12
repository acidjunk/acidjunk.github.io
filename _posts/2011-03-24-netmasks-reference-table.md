---
id: 175
title: Netmasks , reference table
date: 2011-03-24T22:44:53+00:00
author: acidjunk
layout: post
guid: http://www.renedohmen.nl/blog/?p=175
permalink: /2011/03/netmasks-reference-table/
categories:
  - Computerz
---
There are plenty of these netmask references out there, but I prefer my own: hence this table. We&#8217;ve never seen anybody use a network larger than a /4 (256M hosts), so we&#8217;ve truncated the table at that point.

<table border="1">
  <caption>Netmask Quick Reference</caption> <tr>
    <th>
      # bits
    </th>
    
    <th>
      # hosts
    </th>
    
    <th>
      Usable<br /> hosts
    </th>
    
    <th colspan="2">
      netmask
    </th>
    
    <th>
      Cisco mask
    </th>
  </tr>
  
  <tr>
    <td>
      /4
    </td>
    
    <td>
      268435456
    </td>
    
    <td>
      268435454
    </td>
    
    <td colspan="2">
      240.0.0.0
    </td>
    
    <td>
      15.255.255.255
    </td>
  </tr>
  
  <tr>
    <td>
      /5
    </td>
    
    <td>
      134217728
    </td>
    
    <td>
      134217726
    </td>
    
    <td colspan="2">
      248.0.0.0
    </td>
    
    <td>
      7.255.255.255
    </td>
  </tr>
  
  <tr>
    <td>
      /6
    </td>
    
    <td>
      67108864
    </td>
    
    <td>
      67108862
    </td>
    
    <td colspan="2">
      252.0.0.0
    </td>
    
    <td>
      3.255.255.255
    </td>
  </tr>
  
  <tr>
    <td>
      /7
    </td>
    
    <td>
      33554432
    </td>
    
    <td>
      33554430
    </td>
    
    <td colspan="2">
      254.0.0.0
    </td>
    
    <td>
      1.255.255.255
    </td>
  </tr>
  
  <tr>
    <td>
      /8
    </td>
    
    <td>
      16777216
    </td>
    
    <td>
      16777214
    </td>
    
    <td>
      255.0.0.0
    </td>
    
    <td>
      class A network
    </td>
    
    <td>
      0.255.255.255
    </td>
  </tr>
  
  <tr>
    <td>
      /9
    </td>
    
    <td>
      8388608
    </td>
    
    <td>
      8388606
    </td>
    
    <td colspan="2">
      255.128.0.0
    </td>
    
    <td>
      0.127.255.255
    </td>
  </tr>
  
  <tr>
    <td>
      /10
    </td>
    
    <td>
      4194304
    </td>
    
    <td>
      4194302
    </td>
    
    <td colspan="2">
      255.192.0.0
    </td>
    
    <td>
      0.63.255.255
    </td>
  </tr>
  
  <tr>
    <td>
      /11
    </td>
    
    <td>
      2097152
    </td>
    
    <td>
      2097150
    </td>
    
    <td colspan="2">
      255.224.0.0
    </td>
    
    <td>
      0.31.255.255
    </td>
  </tr>
  
  <tr>
    <td>
      /12
    </td>
    
    <td>
      1048576
    </td>
    
    <td>
      1048574
    </td>
    
    <td colspan="2">
      255.240.0.0
    </td>
    
    <td>
      0.15.255.255
    </td>
  </tr>
  
  <tr>
    <td>
      /13
    </td>
    
    <td>
      524288
    </td>
    
    <td>
      524286
    </td>
    
    <td colspan="2">
      255.248.0.0
    </td>
    
    <td>
      0.7.255.255
    </td>
  </tr>
  
  <tr>
    <td>
      /14
    </td>
    
    <td>
      262144
    </td>
    
    <td>
      262142
    </td>
    
    <td colspan="2">
      255.252.0.0
    </td>
    
    <td>
      0.3.255.255
    </td>
  </tr>
  
  <tr>
    <td>
      /15
    </td>
    
    <td>
      131072
    </td>
    
    <td>
      131070
    </td>
    
    <td colspan="2">
      255.254.0.0
    </td>
    
    <td>
      0.1.255.255
    </td>
  </tr>
  
  <tr>
    <td>
      /16
    </td>
    
    <td>
      65536
    </td>
    
    <td>
      65534
    </td>
    
    <td>
      255.255.0.0
    </td>
    
    <td>
      class B network
    </td>
    
    <td>
      0.0.255.255
    </td>
  </tr>
  
  <tr>
    <td>
      /17
    </td>
    
    <td>
      32768
    </td>
    
    <td>
      32766
    </td>
    
    <td colspan="2">
      255.255.128.0
    </td>
    
    <td>
      0.0.127.255
    </td>
  </tr>
  
  <tr>
    <td>
      /18
    </td>
    
    <td>
      16384
    </td>
    
    <td>
      16382
    </td>
    
    <td colspan="2">
      255.255.192.0
    </td>
    
    <td>
      0.0.63.255
    </td>
  </tr>
  
  <tr>
    <td>
      /19
    </td>
    
    <td>
      8192
    </td>
    
    <td>
      8190
    </td>
    
    <td colspan="2">
      255.255.224.0
    </td>
    
    <td>
      0.0.31.255
    </td>
  </tr>
  
  <tr>
    <td>
      /20
    </td>
    
    <td>
      4096
    </td>
    
    <td>
      4094
    </td>
    
    <td colspan="2">
      255.255.240.0
    </td>
    
    <td>
      0.0.15.255
    </td>
  </tr>
  
  <tr>
    <td>
      /21
    </td>
    
    <td>
      2048
    </td>
    
    <td>
      2046
    </td>
    
    <td colspan="2">
      255.255.248.0
    </td>
    
    <td>
      0.0.7.255
    </td>
  </tr>
  
  <tr>
    <td>
      /22
    </td>
    
    <td>
      1024
    </td>
    
    <td>
      1022
    </td>
    
    <td colspan="2">
      255.255.252.0
    </td>
    
    <td>
      0.0.3.255
    </td>
  </tr>
  
  <tr>
    <td>
      /23
    </td>
    
    <td>
      512
    </td>
    
    <td>
      510
    </td>
    
    <td colspan="2">
      255.255.254.0
    </td>
    
    <td>
      0.0.1.255
    </td>
  </tr>
  
  <tr>
    <td>
      /24
    </td>
    
    <td>
      256
    </td>
    
    <td>
      254
    </td>
    
    <td>
      255.255.255.0
    </td>
    
    <td>
      class C network
    </td>
    
    <td>
      0.0.0.255
    </td>
  </tr>
  
  <tr>
    <td>
      /25
    </td>
    
    <td>
      128
    </td>
    
    <td>
      126
    </td>
    
    <td colspan="2">
      255.255.255.128
    </td>
    
    <td>
      0.0.0.127
    </td>
  </tr>
  
  <tr>
    <td>
      /26
    </td>
    
    <td>
      64
    </td>
    
    <td>
      62
    </td>
    
    <td colspan="2">
      255.255.255.192
    </td>
    
    <td>
      0.0.0.63
    </td>
  </tr>
  
  <tr>
    <td>
      /27
    </td>
    
    <td>
      32
    </td>
    
    <td>
      30
    </td>
    
    <td colspan="2">
      255.255.255.224
    </td>
    
    <td>
      0.0.0.31
    </td>
  </tr>
  
  <tr>
    <td>
      /28
    </td>
    
    <td>
      16
    </td>
    
    <td>
      14
    </td>
    
    <td colspan="2">
      255.255.255.240
    </td>
    
    <td>
      0.0.0.15
    </td>
  </tr>
  
  <tr>
    <td>
      /29
    </td>
    
    <td>
      8
    </td>
    
    <td>
      6
    </td>
    
    <td colspan="2">
      255.255.255.248
    </td>
    
    <td>
      0.0.0.7
    </td>
  </tr>
  
  <tr>
    <td>
      /30
    </td>
    
    <td>
      4
    </td>
    
    <td>
      2
    </td>
    
    <td colspan="2">
      255.255.255.252
    </td>
    
    <td>
      0.0.0.3
    </td>
  </tr>
  
  <tr>
    <td>
      /31
    </td>
    
    <td>
    </td>
    
    <td colspan="4">
      point to point links only
    </td>
  </tr>
  
  <tr>
    <td>
      /32
    </td>
    
    <td>
      1
    </td>
    
    <td>
      1
    </td>
    
    <td>
      255.255.255.255
    </td>
    
    <td>
      single IP address
    </td>
    
    <td>
      <em>use <strong>host</strong> notation</em>
    </td>
  </tr>
</table>