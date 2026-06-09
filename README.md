# Caderno Temático: Acessibilidade Web (WCAG + Heurísticas)

> Mini-guia de estudos construído com **NotebookLM** como ferramenta de aprendizagem ativa: curadoria de fontes, engenharia de prompts e consolidação de conhecimento.
> Desafio de Projeto, **DIO**

---

## Contexto e Objetivos

### Assunto escolhido
**Acessibilidade web**, como tornar interfaces utilizáveis por pessoas com deficiência (visual, auditiva, motora, cognitiva) e por usuários em geral, combinando o padrão internacional **WCAG 2.2**, o modelo brasileiro **eMAG** e as **10 heurísticas de usabilidade de Nielsen**.

### Por que este tema
Atuo como UX/UI Designer e Desenvolvedora Full Stack e já fiz curso de acessibilidade, então é um assunto que domino. Escolhi um tema que conheço de propósito: para avaliar com rigor as respostas do NotebookLM, eu precisava saber identificar quando ele estava certo, quando exagerava e quando uma citação não sustentava a afirmação. Em outras palavras, o domínio do conteúdo foi o que me permitiu usar o NotebookLM de forma crítica, e não apenas confiar nele.

### Objetivos com o NotebookLM
- [X] Usar o NotebookLM como ferramenta de estudo ativo, transformando fontes densas num material de consulta rápida.
- [X] Testar engenharia de prompts: comparar formatos (tabela, resumo, comparação) e o efeito de exigir citação e ancoragem nas fontes.
- [X] Avaliar a confiabilidade da ferramenta: verificar se as respostas ficam presas às fontes e se as citações realmente sustentam cada afirmação.
- [X] Provocar e documentar falhas (teste-armadilha) para entender os limites da ferramenta.
- [X] Consolidar um miniguia reaproveitável (resumos, glossário e prompts) para revisões futuras.

---

## Curadoria de Fontes

Foram selecionadas **5 fontes abertas e verificáveis**. Todas foram adicionadas como fontes no NotebookLM.

| # | Fonte | Tipo | Idioma | Link |
|---|-------|------|--------|------|
| 1 | **WCAG 2.2, Web Content Accessibility Guidelines** (especificação oficial, W3C Recommendation) | Página web / norma técnica | EN | https://www.w3.org/TR/WCAG22/ |
| 2 | **WCAG 2 Overview** (introdução acessível da WAI/W3C, ideal para fundamentos) | Página web | EN | https://www.w3.org/WAI/standards-guidelines/wcag/ |
| 3 | **What's New in WCAG 2.2** (os 9 novos critérios explicados) | Página web | EN | https://www.w3.org/WAI/standards-guidelines/wcag/new-in-22/ |
| 4 | **eMAG 3.1, Modelo de Acessibilidade em Governo Eletrônico** (governo federal brasileiro) | PDF | PT-BR | https://emag.governoeletronico.gov.br/emag-3.pdf |
| 5 | **10 Usability Heuristics for User Interface Design** (Nielsen Norman Group) | Página web | EN | https://www.nngroup.com/articles/ten-usability-heuristics/ |

> **Nota de transparência:** todos os links acima foram verificados na web antes de entrar nesta lista. Os documentos do W3C e o eMAG são abertos; o artigo da NN/g é de acesso livre. As datas e versões (WCAG 2.2 de out/2023; eMAG 3.1; heurísticas refinadas em 2020) estão corretas no momento da curadoria, confirme na própria fonte se for citar formalmente.

---

## Engenharia de Prompts e "Cicatrizes"

Aqui registro as perguntas estratégicas feitas ao NotebookLM, as variações testadas, **as respostas reais obtidas** e **as dificuldades** (troubleshooting). Esta seção é o coração do projeto: documenta o raciocínio, não só o resultado.

> Convenção de status: OK = funcionou bem; ATENÇÃO = exigiu reformulação; FALHA = falhou/alucinou.

### Prompt 1: Visão geral estruturada
> "Com base nas fontes, explique os 4 princípios da WCAG e os 3 níveis de conformidade (A, AA, AAA). Para cada princípio, dê 1 exemplo prático de critério de sucesso. Cite a fonte de cada afirmação."

**Variação testada:** trocar "explique" por "monte uma tabela com colunas: Princípio | O que significa | Exemplo de critério | Fonte".

**Resposta obtida (resumida):** O NotebookLM retornou os **4 princípios da WCAG (POUR)**, cada um com um critério de sucesso real como exemplo, todos de **Nível A**:

- **Perceptível** → *1.1.1 Conteúdo não textual (A)*: fornecer alternativa em texto para conteúdo não textual (imagens), permitindo conversão para impressão ampliada, braile, fala ou símbolos.
- **Operável** → *2.1.1 Teclado (A)*: toda a funcionalidade deve ser operável por teclado, para quem não usa mouse.
- **Compreensível** → *3.1.1 Idioma da página (A)*: o idioma padrão da página deve ser determinável programaticamente, para que leitores de tela usem a pronúncia correta.
- **Robusto** → *4.1.2 Nome, Função, Valor (A)*: nome, função e estado dos componentes devem ser determináveis programaticamente, para tecnologias assistivas.

Sobre os **níveis de conformidade**: descreveu **A** (mínimo), **AA** (intermediário, alvo usual das políticas) e **AAA** (mais alto), incluindo a ressalva correta de que **não se recomenda exigir AAA como política geral** para sites inteiros, pois nem todo conteúdo consegue atendê-lo.

Todas as afirmações vieram com **citações clicáveis** apontando para as fontes do W3C, conferido que apontam para o material correto (não houve alucinação).

**[CICATRIZ / Observações]:** Os exemplos vieram **todos em Nível A**. O prompt não pediu variedade de níveis, então não foi erro, mas para enriquecer o caderno seria necessário um prompt extra pedindo exemplos de Nível AA por princípio.

**[Status: OK]**

### Prompt 2: Comparação WCAG 2.1 → 2.2
> "Quais critérios de sucesso a WCAG 2.2 adicionou em relação à 2.1? Liste cada um, explique em 1 frase o problema que resolve e indique o nível (A/AA/AAA). Use apenas as fontes; se algo não estiver nelas, diga 'não consta nas fontes'."

**Variação testada:** acrescentar "para um desenvolvedor front-end, qual o impacto prático de cada um no código?".

**Resposta obtida:** O NotebookLM listou corretamente os **9 novos critérios** da WCAG 2.2, com número, problema que resolve e nível:

| Critério | Nível | Resolve |
|----------|-------|---------|
| 2.4.11 Foco Não Obscurecido (Mínimo) | AA | Elemento em foco não pode ficar totalmente escondido sob banners/conteúdo fixo |
| 2.4.12 Foco Não Obscurecido (Aprimorado) | AAA | Nenhuma parte do elemento em foco pode ser ocultada |
| 2.4.13 Aparência do Foco | AAA | Define tamanho/contraste mínimos do indicador de foco |
| 2.5.7 Movimentos de Arrastar | AA | Oferece alternativa simples (clique) a ações de arrastar |
| 2.5.8 Tamanho do Alvo (Mínimo) | AA | Define dimensão/espaçamento mínimo de áreas clicáveis |
| 3.2.6 Ajuda Consistente | A | Mecanismos de ajuda repetidos aparecem na mesma ordem relativa |
| 3.3.7 Entrada Redundante | A | Evita redigitar informação já fornecida no mesmo processo |
| 3.3.8 Autenticação Acessível (Mínimo) | AA | Login não pode depender só de teste cognitivo |
| 3.3.9 Autenticação Acessível (Aprimorada) | AAA | Versão mais estrita, sem exceções de reconhecimento de objeto/mídia |

Também indicou corretamente que o critério **4.1.1 Parsing** foi tornado obsoleto e removido.

**Distribuição por nível:** 2 critérios em A, 4 em AA, 3 em AAA.

**[VERIFICAÇÃO / Cicatriz metodológica]:** Por ser o ponto onde modelos costumam errar (contar errado os critérios ou trocar níveis), **não confiei cegamente na resposta**: confrontei os 9 critérios um a um contra a fonte oficial (W3C, *What's New in WCAG 2.2*). Resultado: **todos corretos**, sem omissão, invenção ou troca de nível. O teste de alucinação passou, e a citação clicável de cada afirmação apontava para a fonte certa.

**[Status: OK]**. Resposta correta e verificada na fonte.

### Prompt 3: WCAG vs. eMAG (contexto brasileiro)
> "Comparando as fontes, o que o eMAG tem de específico em relação à WCAG? Onde ele se baseia na WCAG e onde diverge? Responda em português."

**Variação testada:** "Sou desenvolvedora no Brasil. Para um site privado (não-governamental), o eMAG é obrigatório? O que as fontes dizem sobre isso?"

**Resposta obtida (resumida):** O NotebookLM estruturou a comparação em 3 eixos:

- **Onde o eMAG se baseia na WCAG:** usa a WCAG 2.0 como alicerce técnico; exige padrões W3C (HTML/CSS); muitas recomendações citam critérios da WCAG (ex.: marcação semântica ligada ao 1.3.1).
- **Divergências:** o eMAG **abandonou os níveis A/AA/AAA** (por ser padrão governamental de cumprimento obrigatório, sem exceções); organiza-se em **seções técnicas** (Marcação, Comportamento, Conteúdo, Apresentação, Multimídia, Formulário) em vez dos 4 princípios; tem foco nas necessidades do governo federal brasileiro.
- **Exclusividades do eMAG:** barra de acessibilidade obrigatória, página de acessibilidade dedicada, atalhos de teclado padronizados, ênfase em formatos abertos (ODF) alinhada ao e-PING, padrões de mapa do site e formulários.

**Validações (confirmadas em fonte):** o embasamento na WCAG 2.0, o abandono dos níveis A/AA/AAA, a organização em seções e os elementos padronizados (barra, página, atalhos, mapa) conferem. **Importante:** o ponto de **obrigatoriedade** foi tratado corretamente, limitado ao âmbito do governo federal (Portaria nº 3/2007), sem extrapolar para sites privados.

**[Verificação por citação, confirmada]:** abri os trechos citados no PDF do eMAG (a fonte). Os dois pontos que inicialmente pareciam possíveis extrapolações se confirmaram **a favor da resposta**:
- **Números dos atalhos:** o eMAG **fixa explicitamente** na seção *3.2 Atalhos de teclado*, "1: para ir ao conteúdo; 2: para ir ao menu principal; 3: para ir à caixa de pesquisa" (e o exemplo de código da barra confirma `[1] [2] [3]`). Não é convenção de implementação: está no documento.
- **Versão:** a fonte é a **versão 3.0** (seção "1.1 Sobre a versão 3.0", embasada na WCAG 2.0). Citar "3.0" foi fiel à fonte. (A versão mais recente publicada é a 3.1, mas isso é externo às fontes, irrelevante para a tarefa.)
- Demais pontos também confirmados no PDF: abandono dos níveis A/AA/AAA, seções de classificação, obrigatoriedade via Portaria nº 3/2007, vínculo de recomendações a critérios WCAG (ex.: Rec. 2 → 1.3.1; Rec. 1 → 4.1.1/4.1.2), e ODF/e-PING com alternativa HTML para PDF (Rec. 22).

**[Status: OK]**. Resposta correta e integralmente ancorada nas fontes; verificação por citação não encontrou nenhuma extrapolação.

### Prompt 4: Acessibilidade × Usabilidade
> "Cruze as 10 heurísticas de Nielsen com os princípios da WCAG. Onde elas se sobrepõem? Onde uma cobre algo que a outra não cobre? Monte uma tabela de correspondência."

**Variação testada:** pedir exemplos concretos de um formulário web (campos, labels, mensagens de erro).

**Resposta obtida (resumida):** O NotebookLM montou uma tabela cruzando as 10 heurísticas de Nielsen com critérios da WCAG, mais uma seção de "lacunas" (o que cada framework cobre que o outro não). Correspondências de destaque: heurísticas 5/9 (erros) → Diretriz 3.3 (Assistência de Entrada); heurística 4 (consistência) → 3.2.3/3.2.4; heurística 3 (controle) → 2.2.2 e 2.1.2; heurística 6 → 3.3.2. Lacunas: WCAG cobre o sensorial (1.1.1, 1.2.2, 1.4.3), o robusto/AT (4.1.2) e reações físicas/convulsões (Diretriz 2.3), pontos que Nielsen não detalha.

**Verificação (números dos critérios):** confiri os critérios citados, incluindo os menos óbvios (4.1.3 Status Messages, 1.4.8 Visual Presentation). **Todos os números estão corretos**, não houve invenção de critério.

**[CICATRIZ, síntese interpretativa + encaixe forçado]:** esta é a observação central e exigiu atenção redobrada. Nenhuma das 5 fontes cruza Nielsen com WCAG (o artigo de Nielsen não cita a WCAG, e vice-versa). Logo, **toda a tabela é uma síntese interpretativa do NotebookLM**, não um fato rastreável a uma citação. As citações numéricas ancoram a heurística (no Nielsen) e o critério (na WCAG) **separadamente**, não a ponte entre eles. Isso é legítimo (o cruzamento foi pedido), mas precisa ser rotulado como interpretação, não como afirmação das fontes.

Além disso, houve **encaixe forçado** em pelo menos dois pares:
- **Heurística 8 (estética/minimalismo) → 1.4.8 (Visual Presentation):** esticado. O 1.4.8 trata de legibilidade de *blocos de texto* (largura, espaçamento, justificação, cores), não de minimalismo estético.
- **Heurística 1 (visibilidade do status) → 4.1.3 (Status Messages):** parcial. O 4.1.3 é o recorte de acessibilidade (anúncio a leitores de tela sem foco), não o conceito amplo de Nielsen.

**Reformulação sugerida (melhora a entrega):** pedir ao NotebookLM para classificar cada correspondência como "Forte / Parcial / Interpretativa" e separar explicitamente o que está nas fontes do que é inferência dele.

**[Status v1: ATENÇÃO]**. Fatos corretos, mas resposta mistura dado citável com síntese não-ancorada e contém encaixes esticados; requer rotulagem honesta no caderno.

**Reformulação aplicada (v2):**
> "Na tabela anterior, marque cada correspondência como 'Forte', 'Parcial' ou 'Interpretativa'. Indique explicitamente quais ligações estão afirmadas nas fontes e quais são inferência sua, já que nenhuma fonte cruza Nielsen com WCAG."

**Resultado da v2:** o NotebookLM (a) abriu reconhecendo que nenhuma fonte cruza os frameworks e que as ligações são inferências; (b) classificou cada par como Forte / Parcial / Interpretativa; (c) marcou ele mesmo a ligação heurística 8 → 1.4.8 como **"Interpretativa / ligação fraca"**, o encaixe forçado que havíamos flagrado; (d) ao final, **separou explicitamente** o que está afirmado nas fontes (as definições de cada heurística e de cada critério) do que é inferência dele (o agrupamento por "Foco", a escolha de qual critério representa cada heurística e a atribuição de "Força"). Critérios novos citados na v2 (2.3.1, 3.1.3, 3.3.4, 3.3.6) verificados, todos corretos.

**[Status v2: OK]**. Após reformulação, a síntese ficou corretamente rotulada e a ligação fraca foi assumida como tal.

**Aprendizado (ciclo de prompt):** quando se pede um cruzamento entre frameworks que nenhuma fonte une, o NotebookLM tende a preencher todas as células e a apresentar inferência com aparência de fato. A correção não é descartar a resposta, e sim **pedir que ele rotule força e separe fonte de inferência**, o que transforma uma tabela "lisa" numa análise honesta e auditável.
> "Com base em tudo, gere um checklist de acessibilidade de 10 itens para revisar uma página web antes de publicar, em ordem de prioridade. Cada item deve indicar a qual critério WCAG ou heurística ele se refere."

**Resposta obtida (resumida):** O NotebookLM gerou um checklist de 10 itens, priorizado, cada um com critério WCAG (e heurística ilustrativa quando cabia): 1) alt em imagens, 1.1.1 (A); 2) navegação por teclado, 2.1.1 (A); 3) título de página descritivo, 2.4.2 (A); 4) idioma declarado (`lang`), 3.1.1 (A); 5) contraste mínimo 4,5:1, 1.4.3 (AA); 6) hierarquia de cabeçalhos, 1.3.1 (A); 7) textos de link significativos, 2.4.4 (A); 8) labels em formulários, 3.3.2 (A); 9) identificação/sugestão de erros, 3.3.1 (A) / 3.3.3 (AA); 10) foco visível, 2.4.7 (AA). Dica de priorização: focar Nível A primeiro; lembrar que no eMAG todas as recomendações são obrigatórias, sem níveis.

**Verificação:** confiri todos os 10 critérios e níveis (incluindo 2.4.2 e 2.4.4, que não tinham aparecido antes). **Todos corretos**, e o valor de contraste 4,5:1 está certo para texto normal em AA.

**[Observação]:** as ligações com heurísticas são secundárias/ilustrativas, a espinha dorsal são os critérios WCAG (factuais e corretos). Mantêm a natureza interpretativa documentada no Prompt 4, mas sem comprometer a utilidade do checklist.

**[Status: OK]**. Checklist correto, bem priorizado e diretamente acionável em revisão de página.
> "Quais são as novidades planejadas para a WCAG 3.0? Use apenas as fontes; se não constar, diga 'não consta nas fontes'."

**Hipótese:** as fontes tratam de WCAG 2.x e heurísticas. Esperava-se a resposta "não consta nas fontes", ou, no pior caso, uma alucinação a ser documentada.

**Resposta obtida:** o NotebookLM listou 4 pontos sobre a WCAG 3.0 (reestruturação substancial; metodologia de design focada em pesquisa e centrada no usuário; escopo incluindo autoria de conteúdo, suporte de user agents e ferramentas de autoria; esforço plurianual) e o codinome "Silver". Foi honesto ao acrescentar que detalhes técnicos finos (critérios de sucesso, modelo de pontuação) **não constam** nas fontes.

**Verificação (a parte importante):** abri os trechos citados, em vez de só confiar na presença da citação. Os detalhes **estavam mesmo nas fontes**: a especificação WCAG 2.2 tem a seção *"Later Versions of Accessibility Guidelines"*, que descreve exatamente esse conteúdo; e o codinome "Silver" aparece no *WCAG 2 Overview*. Ou seja: resposta **ancorada e correta**, sem alucinação.

**Cicatriz (metodológica, a mais valiosa do caderno):** minha hipótese inicial foi de que o NotebookLM havia extrapolado além das fontes. Esse pré-julgamento quase virou um registro de "alucinação" que estava **errado**: só a leitura do trecho citado por inteiro dissolveu o falso positivo. **Lição:** auditar o NotebookLM exige abrir e ler cada citação na fonte; a existência de um número de citação não prova que ele sustenta a frase, e supor o que as fontes contêm (sem ler) produz tanto falso positivo quanto falso negativo.

**[Status: OK]**. Resposta correta e ancorada; o critério "use apenas as fontes" foi respeitado.

### Aprendizados sobre prompting

**O que funcionou melhor: pedir citação de fonte? pedir tabela? limitar às fontes?**
Gostei muito de o NotebookLM citar a fonte de todos os trechos que usa, o que dá segurança para checar cada afirmação. Também achei ótima a liberdade de pedir o formato que eu quiser (tabela, resumo, comparação) sem que ele perca a ancoragem nas fontes.

**O NotebookLM citou trechos fora das fontes em algum momento? Como percebi?**
Não. Em nenhum momento ele citou trechos fora das fontes ou inventou fatos. Nos casos em que a resposta parecia ir além do material (por exemplo, as novidades da WCAG 3.0), ao abrir as citações confirmei que o conteúdo estava mesmo nas fontes.

**Qual reformulação teve o maior ganho de qualidade?**
A do Prompt 4 (cruzamento entre Nielsen e WCAG). Pedir para classificar cada correspondência como Forte / Parcial / Interpretativa e separar o que vinha das fontes do que era inferência transformou uma tabela que misturava fato e interpretação numa análise honesta, com a força de cada ligação explícita.

---

## Miniguia de Estudo (Entrega Final)

### Resumos estruturados

#### 1. WCAG: a base
A WCAG (Web Content Accessibility Guidelines) é o padrão internacional do W3C para acessibilidade de conteúdo web. Organiza-se em **4 princípios** (sigla POUR, em inglês):

- **Perceptível**, a informação e os componentes da interface precisam ser apresentáveis de formas que o usuário consiga perceber (ex.: texto alternativo em imagens, legendas em vídeos, contraste de cor adequado).
- **Operável**, os componentes e a navegação precisam ser operáveis (ex.: tudo acessível por teclado, sem dependência exclusiva do mouse; tempo suficiente para interagir).
- **Compreensível**, informação e operação da interface precisam ser compreensíveis (ex.: linguagem clara, comportamento previsível, ajuda na correção de erros).
- **Robusto**, o conteúdo precisa ser robusto o bastante para funcionar com diferentes tecnologias, incluindo leitores de tela (ex.: HTML semanticamente correto).

**Níveis de conformidade:** **A** (mínimo), **AA** (recomendado e mais cobrado por leis), **AAA** (mais rigoroso, nem sempre alcançável para todo conteúdo).

**WCAG 2.2 (atual):** publicada em out/2023, adicionou 9 critérios de sucesso à 2.1 e tornou obsoleto o critério "4.1.1 Parsing". Os 9 novos critérios são:

| Critério | Nível |
|----------|-------|
| 2.4.11 Foco Não Obscurecido (Mínimo) | AA |
| 2.4.12 Foco Não Obscurecido (Aprimorado) | AAA |
| 2.4.13 Aparência do Foco | AAA |
| 2.5.7 Movimentos de Arrastar | AA |
| 2.5.8 Tamanho do Alvo (Mínimo) | AA |
| 3.2.6 Ajuda Consistente | A |
| 3.3.7 Entrada Redundante | A |
| 3.3.8 Autenticação Acessível (Mínimo) | AA |
| 3.3.9 Autenticação Acessível (Aprimorada) | AAA |

Distribuição: 2 critérios em A, 4 em AA, 3 em AAA. (Verificado contra a fonte What's New in WCAG 2.2.)

#### 2. eMAG: o contexto brasileiro
O eMAG (Modelo de Acessibilidade em Governo Eletrônico) é a especialização brasileira baseada na WCAG, voltada a sites e portais do governo federal, de observância obrigatória nesse âmbito. Traz recomendações organizadas por áreas (marcação, comportamento, conteúdo, apresentação, multimídia, formulários).

Três recomendações de formulário do eMAG (seção 3.5 da fonte) úteis para projetos reais:
- Usar sempre a tag `form`, mesmo quando o formulário tiver um único elemento (ex.: uma caixa de pesquisa).
- Associar as etiquetas (`label`) aos seus campos (`input`) correspondentes.
- Dispor os elementos do formulário no HTML já na ordem correta de navegação, sem usar `tabindex`, e não provocar mudança de contexto quando um elemento recebe o foco.

#### 3. Heurísticas de Nielsen: usabilidade
Dez princípios gerais de design de interação (regras de bolso, não regras rígidas). Acessibilidade e usabilidade se reforçam: uma interface acessível tende a ser mais usável, e vice-versa.

### Glossário

| Termo | Definição |
|-------|-----------|
| **WCAG** | Web Content Accessibility Guidelines, padrão internacional do W3C para acessibilidade web. |
| **W3C / WAI** | World Wide Web Consortium / Web Accessibility Initiative, organização e iniciativa que mantêm a WCAG. |
| **Critério de sucesso** | Afirmação testável (atende / não atende) usada para verificar conformidade com a WCAG. |
| **Níveis A / AA / AAA** | Graus de conformidade da WCAG, do mínimo (A) ao mais rigoroso (AAA). |
| **POUR** | Sigla dos 4 princípios: *Perceivable, Operable, Understandable, Robust*. |
| **eMAG** | Modelo de Acessibilidade em Governo Eletrônico, versão brasileira baseada na WCAG. |
| **Texto alternativo (alt)** | Descrição textual de uma imagem, lida por leitores de tela. |
| **Leitor de tela** | Software que converte conteúdo da tela em voz ou braille (ex.: NVDA, VoiceOver). |
| **Contraste** | Relação de luminância entre texto e fundo; a WCAG exige no mínimo 4,5:1 para texto normal no nível AA (critério 1.4.3). |
| **Navegação por teclado** | Operar toda a interface usando apenas o teclado (Tab, Enter, setas). |
| **Foco visível** | Indicação visual de qual elemento está selecionado durante navegação por teclado. |
| **HTML semântico** | Uso de elementos HTML conforme seu significado (`<button>`, `<nav>`, `<label>`), essencial para o princípio "Robusto". |
| **ARIA** | Accessible Rich Internet Applications, atributos que complementam a semântica HTML para tecnologias assistivas. |
| **Avaliação heurística** | Método de inspeção em que avaliadores checam a interface contra um conjunto de heurísticas. |
| **Heurísticas de Nielsen** | 10 princípios gerais de usabilidade (ver tabela abaixo). |

#### As 10 heurísticas de Nielsen (referência rápida)
1. Visibilidade do status do sistema
2. Correspondência entre o sistema e o mundo real
3. Controle e liberdade do usuário
4. Consistência e padrões
5. Prevenção de erros
6. Reconhecimento em vez de memorização
7. Flexibilidade e eficiência de uso
8. Design estético e minimalista
9. Ajudar os usuários a reconhecer, diagnosticar e recuperar-se de erros
10. Ajuda e documentação

### Prompts reutilizáveis (para revisões futuras)

```
1. "Resuma [TÓPICO] usando apenas as fontes deste caderno. Cite a fonte de cada afirmação. Se algo não constar, escreva 'não consta nas fontes'."

2. "Gere 10 perguntas de revisão (flashcards) sobre [TÓPICO], com resposta curta baseada nas fontes."

3. "Explique a diferença entre [CONCEITO A] e [CONCEITO B] em uma tabela, com base nas fontes."

4. "Crie um checklist prático de [N] itens para aplicar [TÓPICO] em um projeto real, em ordem de prioridade."

5. "Liste todos os pontos onde as fontes divergem ou se complementam sobre [TÓPICO]."

6. "Aja como revisor crítico: aponte onde minha interface fictícia descrita a seguir violaria a WCAG ou as heurísticas de Nielsen: [DESCRIÇÃO]."
```

---

## Licença e créditos das fontes
- WCAG e materiais da WAI: © W3C, uso conforme licença de documentos do W3C.
- eMAG: Departamento de Governo Eletrônico (Brasil), licença Creative Commons (Atribuição-Partilha nos Mesmos Termos).
- 10 Usability Heuristics: © Nielsen Norman Group.

Este caderno é um material de estudo pessoal; os direitos sobre os conteúdos originais permanecem com seus autores.
