
## 🧩 **Runlevels (SysVinit) x Targets (systemd)**

| **Runlevel (SysVinit)** | **Descrição**                               | **Target equivalente (systemd)**       |
| ----------------------- | ------------------------------------------- | -------------------------------------- |
| **0**                   | Halt (desligar o sistema)                   | `poweroff.target`                      |
| **1**                   | Single-user mode (modo de recuperação)      | `rescue.target`                        |
| **2**                   | Multiusuário sem rede (Debian usa com rede) | `multi-user.target` (geralmente usado) |
| **3**                   | Multiusuário com rede (sem GUI)             | `multi-user.target`                    |
| **4**                   | Não utilizado (livre para personalização)   | `multi-user.target` ou custom target   |
| **5**                   | Multiusuário com interface gráfica          | `graphical.target`                     |
| **6**                   | Reboot (reiniciar o sistema)                | `reboot.target`                        |

[[BOOT]]