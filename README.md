# ROTINA

**07:40 - 08:00**

- Ligar os computadores.
- Verificar o consumo da internet:
- Se o consumo estiver alto, provavelmene algum PC está atualizando.

- Ligar os tablets.
- Ligar as TVs e os PCs de senha (saguão e prova de legislação).

**08:00 - 08:20**

- Configurar os serviços do Guichê 13:
- Colocar somente serviços da Receita Federal.

**08:20 - 09:00**

- Atender chamados na UAI e Câmara.

**09:00 - 09:15**

- Pausa para o café.

**09:20 - 12:00**

- Atender chamados na UAI e Câmara.

**12:00 - 13:00**

- Almoço.

**13:00 - 13:05**

- Configurar os serviços do Guichê 13:
- Colocar Receita Federal, SINE (exceto sala SINE) e SEPLAG (recadastramento de inativos).

**13:05 - 15:00**

- Atender chamados na UAI e Câmara.

**15:00 - 15:15**

- Pausa para o café.

**15:15 - 17:00**

- Atender chamados na UAI e Câmara.

---

# INSTRUÇÕES

### Configuração do Browser do Guichê 01

O Guichê 01 acessa sites que precisam ser abertos no **modo de compatibilidade do Edge**. Para isso, é necessário adicionar os endereços que estão no servidor de arquivos do CPD, dentro da pasta **SIAEX** (verificar o nome correto). Essa configuração precisa ser feita uma vez por mês.

### Impressora térmica

Os PCs que utilizam essa impressora executam automaticamente um arquivo de impressão ao ligar. Às vezes, essa execução não ocorre de maneira automática, sendo necessário abrir o arquivo baixado (quando os atendentes clicam para imprimir) e executá-lo com o **JAVA**.

> **Obs.:** Para acessar a pasta de inicialização automática, digite o comando abaixo:
> `Win + R` (ou digite Executar no menu iniciar) e depois `shell:startup`.

### Computadores e Tablets

- Os computadores do PROCON (exceto o do Guichê 11 e o de Rosa) são de **responsabilidade da Prefeitura**. Se for preciso fazer algum tipo de manutenção ou troca de peças/periféricos, os funcionários precisam abrir um chamado.
- Os computadores da Identificação são de **responsabilidade da VALID**. Não podemos fazer qualquer tipo de atualização ou manutenção neles, a menos que a VALID solicite ou permita.
- **TODOS** os computadores e impressoras devem ficar na rede da PRODEMGE. A internet da Tropical só deve ser usada nos computadores dos guichês, retaguarda e recepção se a internet da PRODEMGE estiver indisponível (ambos os links).
- Os tablets devem ser retirados do carregador no final do expediente e colocados novamente no início do dia.

### Atualizações do Windows

- Como o link da PRODEMGE na UAI possui apenas 10 Megas, qualquer atualização do Windows consome toda a banda e deixa a internet **muito** lenta. Sendo assim, a solução é desativar as atualizações. Isso pode ser feito com o programa **[Windows Update Blocker (WUB)](https://github.com/Hudrig0/Windows-Update-Blocker/blob/main/Wub_x64.exe)**.
- Se for necessário fazer alguma atualização no Windows, basta desativar o bloqueio no próprio WUB e atualizar o SO.
- Atualmente (01/01/2026), os computadores estão com as atualizações **pausadas**. Em algum momento será necessário atualizar, portanto, antes que o prazo expire, use o WUB para desativar as atualizações definitivamente.

### Windows e Office

O link antigo para download do Windows e Office que está no servidor de arquivos da UAI não funciona mais. Os novos links são:

- [Windows 11](https://massgrave.dev/windows_11_links)
- [Pacote Office](https://massgrave.dev/office_c2r_links)

Para ativar o Windows e Office, abra o PowerShell como administrador e copie o comando:
`irm https://get.activated.win | iex`

Se o código acima estiver bloqueado (pelo provedor de internet/DNS), tente este comando (requer Windows 10 ou 11 atualizado):
`iex (curl.exe -s --doh-url https://1.1.1.1/dns-query https://get.activated.win | Out-String)`

Após isso, o menu de ativação aparecerá.

### Browser de Prova de Legislação

Caso seja necessário instalar o browser de prova novamente, o manual está dentro da pasta "UAI" no servidor de arquivos.

---
