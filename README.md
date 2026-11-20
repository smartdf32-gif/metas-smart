# Metas Smart Soluções

App para apurar as metas e premiações da equipe da Smart Soluções.
O app fica no GitHub Pages e os dados ficam na planilha **Base de Metas - Smart Soluções**, na pasta *Planejamento de Metas* do Google Drive.

## Instalação (uma vez só)

### 1. Ligar a planilha ao app (Apps Script)
1. Abra a planilha **Base de Metas - Smart Soluções**.
2. Menu **Extensões > Apps Script**.
3. Apague o que estiver no editor e cole todo o conteúdo do arquivo `Code.gs`.
4. Na linha `const PIN = 'TROQUE-ESTE-PIN';` troque pelo seu PIN (ex.: `'smart4682'`). Salve (ícone de disquete).
5. Clique em **Implantar > Nova implantação**. Na engrenagem, escolha **App da Web**.
   - Executar como: **Eu**
   - Quem pode acessar: **Qualquer pessoa**
6. Clique em **Implantar**, autorize com sua conta Google (em "Avançado", clique em "Acessar projeto").
7. Copie a **URL do app da Web** (termina em `/exec`).

> Se mudar o código depois, use **Implantar > Gerenciar implantações > editar (lápis) > Nova versão**, para manter a mesma URL.

### 2. Publicar o app no GitHub
1. Entre no GitHub e clique em **New repository**. Nome: `metas-smart`. Deixe **Public** e crie.
2. Clique em **uploading an existing file**, arraste `index.html` e `README.md` e clique em **Commit changes**.
3. Vá em **Settings > Pages**. Em *Branch*, escolha `main` e `/ (root)` e clique em **Save**.
4. Em 1 a 2 minutos o app fica em `https://SEU-USUARIO.github.io/metas-smart/`.

### 3. Primeiro acesso
Abra o link do app, cole a URL do Apps Script e o PIN. Isso fica salvo no aparelho.
O PIN e a URL **não** ficam no GitHub, então o repositório pode ser público.

## Criar uma campanha nova (todo mês)

Tudo é feito na aba **Campanhas** da planilha. Cada linha é uma faixa de uma meta.
O jeito mais rápido: copie as linhas do ciclo anterior, cole embaixo e troque o que mudou.

| Coluna | O que colocar |
|---|---|
| ciclo | Código do ciclo, ex.: `2026-12` (o mês em que o ciclo termina) |
| ciclo_nome | Nome que aparece no app, ex.: `21/11 a 20/12/2026` |
| inicio / fim | Datas do ciclo no formato `2026-11-21` |
| secao | Grupo no app, ex.: `1. Semanais coletivas` |
| ordem | Ordem de exibição da meta |
| codigo | Identificador curto e único da meta no ciclo, ex.: `sem1`, `mes`, `tvbox` |
| meta | Nome da meta |
| periodo | Texto livre, ex.: `21/11 a 27/11` |
| escopo | `loja` (um valor para a loja toda, prêmio para cada um) ou `individual` (valor por vendedor) |
| tipo_valor | `reais`, `quantidade` ou `sim_nao` |
| faixa | Nome da faixa (Bronze, Prata, Meta...) |
| minimo | Valor ou quantidade mínima da faixa |
| premio | Prêmio em reais da faixa |
| so_quem_participou | `sim` quando só ganha quem trabalhou (ex.: bônus do fim de semana) |
| exclui_se_bateu | Código de outra meta: se o vendedor bateu aquela, não ganha esta (ex.: apoio) |
| pagamento | Quando paga |
| observacao | Regras extras |

Regras do cálculo:
- Em cada meta vale só a **maior faixa** atingida (as faixas não somam).
- Para medir o faturamento individual mês a mês nas métricas, use sempre o código **`mes`** para a meta de faturamento individual.
- Use sempre os mesmos códigos para metas parecidas (`google`, `videos`, `parcerias`, `tvbox`...), assim as métricas comparam os meses.

## Vendedores
Aba **Vendedores**: para tirar alguém do app, mude `ativo` para `nao`. Para incluir, adicione uma linha.

## Onde ficam os dados
Aba **Lancamentos**: cada valor digitado no app vira uma linha (ciclo, código, vendedor, valor). Não apague essa aba, ela é o histórico usado nas métricas.
