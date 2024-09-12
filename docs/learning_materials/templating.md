# Templating in Automation

## Jinja Templating

As you enter the automation world, you inevitably learn about Jinja templates.

[Jinja](https://jinja.palletsprojects.com/) is a **templating engine** that, with the help of a programming language like Python, can be used to create network configuration like this:

```
interface GigabitEthernet0/1
 description Uplink to ISP
 ip address 192.168.1.1 255.255.255.0
 no shutdown
!
router ospf 1
 network 192.168.1.0 0.0.0.255 area 0
```

From a template like this:

```
interface {{ interface_name }}
 description {{ description }}
 ip address {{ ip_address }} {{ subnet_mask }}
{% if shutdown %}
 shutdown
{% else %}
 no shutdown
{% endif %}
!
router ospf {{ ospf_process_id }}
 network {{ network }} {{ wildcard_mask }} area {{ area }}
```

This is a rudimentary example. However, you may be thinking,
- What if I have different platforms with different syntax?
- Can I do for-loops for interfaces?
- What about secret keys?
- How do I give the templates my variables in the first place?

Questions like these are why examples can be helpful! This section is intended to be a landing area for examples across the network automation community. With enough examples, it gets easier to analyze and build what works for you and your institution.

For those with templates already, this is your [call to action](#contributing) to contribute your own examples!

### Dartmouth College

[Github Link to Templates](https://github.com/Network-Automation-Forum/handyinfo/tree/main/docs/learning_materials/materials/dartmouth-device-templates)

??? quote "README"
    {%
    include-markdown "learning_materials/materials/dartmouth-device-templates/README.md" 
    %}


### Your Institution Here

!!! quote "Your README"
    Look how cool you'll be.

### Contributing

Use the handy link at the top-right to reach the Network Automation Forum's [handyinfo repository](https://github.com/Network-Automation-Forum/handyinfo) (that's this site!)

Clone the repository, create a branch, add your awesome templates to this section, and then submit your [pull request](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-a-pull-request) to be merged in. Learn more on how to contribute at our [README](https://github.com/Network-Automation-Forum/handyinfo/tree/main).