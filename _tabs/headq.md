---
layout: page
icon: fas fa-server
order: 6
title: HeadQ
description: My Homelab Setup
---
*My Homelab Setup*

<iframe src="https://tcan.betteruptime.com/badge?theme=dark" width="500" height="30" frameborder="0" scrolling="no" style="color-scheme: normal"></iframe>


## Services

  <div style="display:flex;gap:20px;justify-content:left;align-items:center;">
    <button 
      style="display:flex;align-items:center;justify-content:center;padding:10px 20px;background-color:#007bff;color:white;border-radius:5px;font-weight:bold;font-size:14px;cursor:pointer;border:none;text-transform:uppercase;"
      onclick="redirect('https://pi.onetincan.tech')">
      <img src="/assets/img/dashy.png" alt="Dashy Logo" style="width:20px;height:20px;margin-right:10px;">
      Dashy
    </button>

    <button 
      style="display:flex;align-items:center;justify-content:center;padding:10px 20px;background-color:orange;color:white;border-radius:5px;font-weight:bold;font-size:14px;cursor:pointer;border:none;text-transform:uppercase;"
      onclick="redirect('https://grafana.onetincan.tech')">
      <img src="/assets/img/grafana2.svg" alt="Grafana Logo" style="width:20px;height:20px;margin-right:10px;">
      Grafana
    </button>

    <button 
      style="display:flex;align-items:center;justify-content:center;padding:10px 20px;background-color:blue;color:white;border-radius:5px;font-weight:bold;font-size:14px;cursor:pointer;border:none;text-transform:uppercase;"
      onclick="redirect('https://portainer.onetincan.tech')">
      <img src="/assets/img/portainer.svg" alt="Portainer Logo" style="width:20px;height:20px;margin-right:10px;">
      Portainer
    </button>

    <button 
      style="display:flex;align-items:center;justify-content:center;padding:10px 20px;background-color:grey;color:white;border-radius:5px;font-weight:bold;font-size:14px;cursor:pointer;border:none;text-transform:uppercase;"
      onclick="redirect('https://prometheus.onetincan.tech')">
      <img src="/assets/img/prom.svg" alt="Prometheus Logo" style="width:20px;height:20px;margin-right:10px;">
      Prometheus
    </button>
  </div>

<script>
function redirect(url) {
    window.location.href = url;
}
</script>

## APIs

- [CPsched Contests API](cpsched.onetincan.tech)


## Grafana Dashboard
<iframe src="https://grafana.onetincan.tech/public-dashboards/389dbd2e34ac47858380bf0a34fd5cf1" width="1100" height=5000>
</iframe>
