<div id="top">

<p align="center">

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://i.imgur.com/QRlCrO3.png">
  <source media="(prefers-color-scheme: light)" srcset="https://i.imgur.com/QRlCrO3.png">
  <img alt="KellerSS Logo" src="https://i.imgur.com/QRlCrO3.png" width="60%">
</picture>

</p>

<p align="center">
  <em>Pensado e realizado em prol da comunidade de FreeFire, por KellerSS.</em>
</p>

</div>

<img src="https://i.imgur.com/NnWf7Fm.png" alt="line break" width="100%" height="3px">

## IntroduÃ§Ã£o

KellerSS Ã© um scanner para dispositivos **iOS** que tem o objetivo de analisar o relatÃ³rio de privacidade do iPhone e identificar conexÃµes suspeitas de proxy e cheat em questÃ£o de segundos.

**Por que usar o KellerSS?**

O projeto tem como principal funÃ§Ã£o facilitar o trabalho dos analistas em suas triagens, com diversas funÃ§Ãµes automatizadas:

* **ðŸ”µ AutomaÃ§Ã£o:** O scanner faz todo o trabalho pesado por vocÃª, poupando seu tempo.
* **âš«ï¸ DetecÃ§Ã£o de Proxy:** Identifica IPs de VPS, Hosting e Proxy usados por cheaters.
* **ðŸŸ£ Facilidade:** Roda diretamente no iPhone usando o app **Scriptable**, sem necessidade de computador.

<img src="https://i.imgur.com/NnWf7Fm.png" alt="line break" width="100%" height="3px">

## Como utilizar?

#### <img width="2%" src="https://simpleicons.org/icons/apple.svg">&emsp13; Passo 1 â€” Instale o Scriptable:

| Aplicativo | DescriÃ§Ã£o |
|---|---|
| [Scriptable](https://apps.apple.com/br/app/scriptable/id1405459188) | App gratuito para automaÃ§Ã£o iOS com JavaScript |

#### <img width="2%" src="https://simpleicons.org/icons/apple.svg">&emsp13; Passo 2 â€” Exporte o RelatÃ³rio de Privacidade do iPhone:

VÃ¡ em **Ajustes â†’ Privacidade e SeguranÃ§a â†’ RelatÃ³rio de Privacidade de Apps â†’ Exportar RelatÃ³rio de Privacidade de Apps**

O arquivo serÃ¡ salvo no formato `App_Privacy_Report_v4_YYYY-MM-DD...` no iCloud Drive.

#### <img width="2%" src="https://simpleicons.org/icons/gnometerminal.svg">&emsp13; Passo 3 â€” Instale o scanner no Scriptable:

Abra o Scriptable, crie um novo script, cole o cÃ³digo abaixo e salve:

```js
const KELLERSS_IOS = "https://raw.githubusercontent.com/kellerzz/KellerSS-iOS/refs/heads/main/KellerSS-iOS.js"

let req = new Request(KELLERSS_IOS)
let code = await req.loadString()

if (!code || code.startsWith("404")) {
  let a = new Alert()
  a.title = "Erro"
  a.message = "Nao foi possivel baixar o script."
  a.addAction("OK")
  await a.present()
} else {
  eval(code)
}
```

#### <img width="2%" src="https://simpleicons.org/icons/gnometerminal.svg">&emsp13; Passo 4 â€” Execute:

Toque no script para rodar. O app irÃ¡ abrir o seletor de arquivos â€” selecione o `App_Privacy_Report` exportado. A anÃ¡lise inicia automaticamente.

<img src="https://i.imgur.com/NnWf7Fm.png" alt="line break" width="100%" height="3px">

## DetecÃ§Ãµes

| DetecÃ§Ã£o | DescriÃ§Ã£o |
|---|---|
| `App Proxy/Cheat` | Detecta apps conhecidos de proxy como PotatsoLite e ProxyFF |
| `IPs de VPS/Hosting` | Identifica servidores VPS, Hosting e Proxy por ASN, ISP e rDNS |
| `ASN de Cheat Proxy` | Cruza ASNs conhecidos como Hostinger (AS47583) e Multacom (AS35916) |
| `TLD Suspeito` | Detecta domÃ­nios com extensÃµes suspeitas como `.site`, `.store`, `.xyz` |
| `DomÃ­nio Suspeito` | Identifica palavras-chave no domÃ­nio como `proxy`, `cheat`, `mitm`, `tunnel` |
| `HTTP Probe` | Verifica se o servidor responde com banners suspeitos como nginx, apache, ubuntu |
| `Proxy antes do login` | Cruza conexÃµes suspeitas com o timestamp de abertura do Free Fire |
| `Ãšltimo login Free Fire` | Detecta a Ãºltima inicializaÃ§Ã£o do jogo via `app-measurement.com` |
| `Apple Store aberta` | Detecta abertura da App Store â€” se apÃ³s a partida, aplique o W.O |
| `Arquivo antigo` | Alerta se o Ãºltimo registro do relatÃ³rio Ã© de mais de 15 minutos atrÃ¡s |
| `Uptime curto` | Alerta se o relatÃ³rio cobre menos de 20 minutos de atividade |
| `ValidaÃ§Ã£o do arquivo` | Verifica se o arquivo Ã© um App Privacy Report legÃ­timo e nÃ£o adulterado |

<img src="https://i.imgur.com/NnWf7Fm.png" alt="line break" width="100%" height="3px">

## ContribuiÃ§Ãµes

ContribuiÃ§Ãµes sÃ£o bem vindas! Por favor me chame no privado do discord `keller22cao`.

* **ðŸ› [Reporte um Problema](https://discord.gg/allianceoficial)**: Encontrou um bug? Me avise!
* **ðŸ’¬ [FaÃ§a uma sugestÃ£o](https://discord.gg/allianceoficial)**: Tem ideias ou sugestÃµes? Eu adoraria lhe ouvir.

<br>

## Agradecimentos

Um grande agradecimento aos membros abaixo por seu trabalho incrÃ­vel e contribuiÃ§Ãµes:

<div style="text-align:; font-weight: bold; margin-bottom: 10px;">
  ã…¤Kellerã…¤ã…¤Katiauã…¤ Samir
</div>

<table>
  <tr>
    <td style="text-align: center; margin-right: 20px;">
      <a href="https://www.instagram.com/kellerffx">
        <img src="https://i.imgur.com/25Qrvbh.png" alt="Keller" style="width: 50px; height: 50px;">
      </a>
    </td>
    <td style="text-align: center; margin-right: 20px;">
      <a href="https://discord.gg/allianceoficial">
        <img src="https://i.imgur.com/e4H6PaP.png" alt="Katiau" style="width: 50px; height: 50px; object-fit: cover;">
      </a>
    </td>
    <td style="text-align: center;">
      <a href="https://discord.gg/allianceoficial">
        <img src="https://i.imgur.com/OWo75s4.png" alt="Samir" style="width: 50px; height: 50px;">
      </a>
    </td>
  </tr>
</table>

<img src="https://i.imgur.com/NnWf7Fm.png" alt="line break" width="100%" height="3px">

## ðŸŽ— LicenÃ§a

Copyright KellerSS Â© 2025-2030.

<div align="left">
</div>

<img src="https://i.imgur.com/NnWf7Fm.png" alt="line break" width="100%" height="3px">
