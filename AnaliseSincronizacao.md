# Relatório de Análise de Threads em Java

## 🔹 Análise 1 

O programa foi executado duas vezes gerando duas logs diferentes em ambas as execuções, o comportamento das theads Produtora e consumidora foi identico:
 Os valores foram produzidos e consumidos de forma alternada e ordenada, sem interferencia ou inconsistencia em seus dados.
 isso demonstra que a cincronização implementda com a palavra chave synxhronized funcionou corretamente, garantindo acesso exclusivo a variavel compartilhada dado
 e evitando condições de corrida 

 concluindo que o código esta cincronizando e apresentando resultados consistentes e previsiveis em todas as execuções.
 
---

## 🔹 Análise 2 – Threads sem sincronização x Monitor

Nas execuções da pasta `atividade1`, observamos threads **sem sincronização**, onde o produtor e o consumidor atuam de forma desordenada.  
Já na pasta `monitor`, o uso de **monitores** garante a sincronização correta.  
Além disso, nas execuções sem sincronização há risco de **condições de corrida e perda de dados**, pois o produtor continua trabalhando sem esperar o consumidor.  
Na versão com monitor, as threads cooperam, mantendo a ordem, **consistência dos dados** e controle do acesso ao recurso compartilhado.

---

## 🔹 Análise 3 – Comparação entre Threads Simples, Monitor e Eventos

Foram testadas três formas de fazer o produtor e o consumidor trabalharem juntos em Java: **threads simples**, **monitor** e **eventos**.  

- **Threads simples:** tudo roda ao mesmo tempo, mas sem controle. Produtor e consumidor podem se atropelar, causando erros.  
- **Monitor:** mais organizado. Um espera o outro terminar antes de continuar, garantindo segurança, mas deixando a execução um pouco mais lenta.  
- **Eventos:** mais equilibrado. As duas partes se comunicam bem, trocando informações sem travar, combinando **velocidade e segurança**.

> Conclusão: eventos deram o melhor resultado, monitores garantiram mais segurança, e threads simples servem principalmente para entender o funcionamento básico.

---

##  Análise Técnica e Opinião Pessoal

Testando os três programas — **Threads Simples**, **Monitor** e **Eventos** — ficou claro como a **sincronização muda completamente o comportamento das threads** e a integridade dos dados.

- Sem sincronização, o produtor e o consumidor podem se atropelar, os dados ficam desordenados e há risco de **condições de corrida**.  
- Com monitor (`synchronized`, `wait()` e `notify()`), as threads esperam sua vez, garantindo **dados consistentes** e execução previsível, mesmo que um pouco mais lenta.  
- Com eventos, as threads se comunicam de forma fluida, mantendo **dados corretos** e a execução rápida, equilibrando **velocidade e confiabilidade**.

> Em resumo: sincronização é essencial para que programas multithread funcionem corretamente. Sem ela, os resultados são imprevisíveis; com ela, os dados ficam seguros e a execução organizada.  

---

## Opinião Geral

Analisando os três casos juntos, fica claro que a **sincronização é essencial** para manter a **integridade dos dados** e a **ordem de execução**:

- **Sem sincronização**, os dados ficam desordenados e podem ser perdidos.  
- **Com monitor**, há segurança e previsibilidade, mas a execução pode ser um pouco mais lenta.  
- **Com eventos**, é possível manter **dados corretos** e ainda ter uma execução rápida e fluida.  

> Cada abordagem tem seu propósito: threads simples para aprendizado, monitor para segurança e eventos para **equilíbrio entre velocidade e confiabilidade**.

