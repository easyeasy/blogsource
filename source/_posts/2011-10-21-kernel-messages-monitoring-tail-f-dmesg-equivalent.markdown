---
layout: post
title: "Kernel messages monitoring: tail -f dmesg Equivalent"
date: 2011-10-21 09:40
comments: true
categories: programming 
---
For a kernel module development project I worked on, I need to monitor the 'dmesg' output continually. The solution is as following:

{% codeblock %}
while true;do dmesg -c; done
{% endcodeblock %}

Note: Running dmesg -c will clear the dmesg ring buffer contents after printing, so you will lose the contents of dmesg.

There is another solution found on the web as following, but doesn't work for me.

{% codeblock %}
echo "9 9 9 9" > /proc/sys/kernel/printk
{% endcodeblock %}


