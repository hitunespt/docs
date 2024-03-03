## CISCO NEXUS
**Adicionar vlan ao trunk no port-channel5:**
    
    conf t
    int po5
    switchport trunk allowed vlan add 109

**Criar vlan no Nexus:**

    conf t
    vlan 109
    name ACS_SRV_MUNI

**Adicionar vlan ao trunk dos hosts upesxint:**
    
    conf t

    int po29
    switchport trunk allowed vlan add 109

    int po31
    switchport trunk allowed vlan add 109

    int po33
    switchport trunk allowed vlan add 109

    int po235
    switchport trunk allowed vlan add 109

    int po37
    switchport trunk allowed vlan add 109

    int po39
    switchport trunk allowed vlan add 109
    
**Adicionar vlan ao trunk dos hosts upesxora:**

    int po41
    switchport trunk allowed vlan add 109

    int po43
    switchport trunk allowed vlan add 109
    

## VMWare
**Adicionar vlan aos port groups dos hosts upesxint:**\
https://upesxint01.olisipo.net/ui/#/host/networking/portgroups \
https://upesxint02.olisipo.net/ui/#/host/networking/portgroups \
https://upesxint03.olisipo.net/ui/#/host/networking/portgroups \
https://upesxint04.olisipo.net/ui/#/host/networking/portgroups \
https://upesxint05.olisipo.net/ui/#/host/networking/portgroups \
https://upesxint06.olisipo.net/ui/#/host/networking/portgroups

**Adicionar vlan aos port groups dos hosts upesxora:**\
https://upesxora01.olisipo.net/ui/#/host/networking/portgroups \
https://upesxora02.olisipo.net/ui/#/host/networking/portgroups
