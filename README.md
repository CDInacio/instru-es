# Manual de Operações e Rotina de TI – UAI e Câmara

Este documento reúne os procedimentos diários, políticas de uso de equipamentos e instruções técnicas para a manutenção do ambiente de TI.

## Rotina Diária

### **Manhã**

**07:40 – 08:00 | Preparação do Ambiente**

- **Verificação de Rede:** Antes de tudo, cheque o consumo de banda da internet.
- _Dica:_ Se o consumo estiver anormalmente alto, é muito provável que algum PC esteja baixando atualizações do Windows. Identifique e corrija.

- **Inicialização:**
- Ligar todos os computadores.
- Ligar os tablets.
- Ligar as TVs e os PCs de senha (Saguão e Sala de Prova de Legislação).

**08:00 – 08:20 | Configuração Específica (Guichê 13)**

- Configurar os serviços disponíveis no painel: **Apenas serviços da Receita Federal**.

**08:20 – 09:00 | Suporte Técnico**

- Atendimento a chamados e demandas na UAI e Câmara.

**09:00 – 09:15 | Pausa**

- Café / Descanso.

**09:20 – 12:00 | Suporte Técnico**

- Continuação dos atendimentos na UAI e Câmara.

### **Tarde**

**12:00 – 13:00 | Almoço**

**13:00 – 13:05 | Reconfiguração (Guichê 13)**

- Atualizar os serviços disponíveis no painel para incluir:
- Receita Federal.
- SINE (exceto sala SINE).
- SEPLAG (Recadastramento de inativos).

**13:05 – 15:00 | Suporte Técnico**

- Atendimento a chamados na UAI e Câmara.

**15:00 – 15:15 | Pausa**

- Café / Descanso.

**15:15 – 17:00 | Encerramento**

- Atendimento final de chamados.
- **Importante:** Ao final do expediente, retirar os tablets dos carregadores (eles devem ser reconectados apenas no início do dia seguinte).

---

## Infraestrutura e Hardware

### **Responsabilidade Patrimonial e Manutenção**

Para evitar conflitos de contrato, verifique a propriedade do equipamento antes de qualquer manutenção:

1. **PCs do PROCON:**

- A maioria pertence à **Prefeitura** (exceto Guichê 11 e o computador da Rosa).
- _Procedimento:_ Para manutenção ou troca de peças, os funcionários devem abrir chamado no sistema da prefeitura.

2. **PCs da Identificação:**

- Pertencem à **VALID**.
- _Atenção:_ **Não realize** atualizações ou manutenções físicas nestas máquinas sem solicitação ou permissão expressa da VALID.

3. **PCs da Junta Militar:**

- Apenas o computador da **Retaguarda** pertence à Prefeitura.

4. **Demais Computadores:**

- O restante pertence à **UAI (Câmara)**.

### **Política de Rede (Internet)**

- **Rede Principal:** Todos os computadores e impressoras devem operar preferencialmente na rede da **PRODEMGE**.
- **Rede de Contingência (Tropical):** O uso é restrito. Deve ser utilizada nos guichês, retaguarda e recepção **apenas** se a PRODEMGE ficar indisponível (queda de ambos os links).

### **Configurações de Rede (IP e DNS)**

Utilize os parâmetros abaixo para configuração de IP estático quando necessário:

| Configuração           | Rede PRODEMGE (Padrão)                   | Rede Tropical (Contingência e wifi) |
| ---------------------- | ---------------------------------------- | ----------------------------------- |
| **Endereço IP**        | `10.82.167.X`                            | `192.168.3.X`                       |
| **Máscara (Sub-rede)** | `255.255.255.0` (/24)                    | `255.255.255.0` (/24)               |
| **Gateway Padrão**     | `10.82.167.1`                            | `192.168.3.1`                       |
| **DNS Preferencial**   | `200.198.5.5`                            | `8.8.8.8`                           |
| **DNS Alternativo**    | `200.168.5.4`                            | `8.8.4.4`                           |
| **Proxy de Rede**      | `http://proxy.prodemge.gov.br/proxy.pac` | _Não utiliza proxy_                 |

---

## Software e Sistemas

### **Gerenciamento de Atualizações (Windows Update)**

Devido à limitação do link da PRODEMGE (10 Megas), atualizações automáticas consomem toda a banda, deixando a internet muito lenta.

- **Política:** Manter o Windows Update **desativado**.
- **Ferramenta:** Utilize o **[Windows Update Blocker (WUB)](https://github.com/Hudrig0/Windows-Update-Blocker/blob/main/Wub_x64.exe)**.
- **Procedimento para Atualizar:** Caso seja necessário atualizar uma máquina, desbloqueie via WUB, realize a atualização e bloqueie novamente em seguida.
- _Status (01/01/2026):_ Máquinas com atualizações pausadas. Planeje uma janela de manutenção para atualizar e bloquear definitivamente antes que o prazo de pausa expire.

### **Ativação e Instalação (Windows e Office)**

Os links antigos do servidor estão obsoletos. Utilize os métodos abaixo:

- **Download:**
- [Windows 11](https://massgrave.dev/windows_11_links)
- [Pacote Office](https://massgrave.dev/office_c2r_links)

- **Ativação (Script Massgrave):**
  Abra o PowerShell como Administrador e execute:

```powershell
irm https://get.activated.win | iex

```

_Se houver bloqueio de DNS, use o comando alternativo:_

```powershell
iex (curl.exe -s --doh-url https://1.1.1.1/dns-query https://get.activated.win | Out-String)

```

### **Configurações Específicas de Navegadores**

1. **Guichê 01 (Modo de Compatibilidade):**

- Sites específicos precisam abrir no modo IE/Compatibilidade do Edge.
- **Ação:** Atualizar mensalmente a lista de sites no modo de compatibilidade. O arquivo com os links que precisam ser adicionados estão no servidor de arquivos do CPD, pasta **SIAEX**.

2. **Prova de Legislação:**

- Caso precise reinstalar o browser de prova, consulte o manual localizado na pasta "UAI" no servidor de arquivos.

---

## Solução de Problemas Comuns

### **Impressora Térmica (Falha de Inicialização)**

Alguns PCs possuem um script de impressão que deve iniciar com o Windows. Se a impressão falhar:

1. Verifique se o script rodou.
2. Se não, localize o arquivo baixado e execute-o manualmente utilizando o **JAVA**.

> **Dica:** Para verificar ou adicionar itens à inicialização automática:
> Pressione `Win + R` e digite `shell:startup`.

### **Sistemas VALID e SIP (Lentidão)**

Estes sistemas apresentam instabilidade frequente. Antes de abrir chamado técnico para o fornecedor:

1. Verifique a latência (ping) e o consumo de banda da internet local.
2. Se a rede interna estiver ok, o problema é na aplicação (servidor externo).

### **Setor de Identidade (Impressoras e Scanners)**

Há uma dificuldade recorrente dos atendentes com o uso dos periféricos.

- **Ação Recomendada:** Realizar acompanhamento próximo e reforçar o treinamento operacional com a equipe.

---

## Credenciais e Acessos

| Recurso                             | Senha / Detalhe | Observação                     |
| ----------------------------------- | --------------- | ------------------------------ |
| **Wi-Fi**                           | `Uaijm!@#`      | Rede corporativa               |
| **Guichês 11, 12, 13, 14**          | `uaijm4454`             | Senha padrão                   |
| **Guichê 02 (Trânsito)**            | `123456`        | _Verificar se usuário alterou_ |
| **Guichês 4, 5, 6, 7 (Identidade)** | `123456`        | Senha padrão                   |
| **ADM Identidade**                  | `V@l1d#2021`    | Acesso administrativo          |

> **Nota:** Alguns usuários (Ex: Rosa/PROCON, Vinícios/Trânsito) podem ter alterado suas senhas locais.

---

## Postura e Atendimento ao Usuário

Ao lidar com usuários que apresentam maior dificuldade tecnológica (como Madalena, Juliana, Regina, entre outros):

- **Foco na Autonomia:** Evite realizar tarefas rotineiras _pelo_ usuário (ex: usar iLovePDF, comprimir arquivos, mudar resolução de impressão).
- **Abordagem Educativa:** Tenha paciência, sente-se ao lado e ensine o passo a passo. O objetivo é que elas aprendam a executar sozinhas. Se fizermos por elas, cria-se uma dependência insustentável para a equipe de TI.
