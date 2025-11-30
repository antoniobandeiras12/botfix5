# Sistema RSO - Formulário com Integração Discord

## Objetivo
Criar um formulário de envio de relatório de patrulhamento que integra com bot Discord, removendo banco de dados e painel de admin.

## Fases do Projeto

### Fase 1: Remover Banco de Dados e Admin
- [ ] Remover tabelas do banco de dados
- [ ] Remover procedures tRPC de CRUD
- [ ] Remover página de admin dashboard
- [ ] Remover página de admin login
- [ ] Remover autenticação OAuth
- [ ] Simplificar routers tRPC

### Fase 2: Reescrever Formulário
- [x] Manter formulário multi-passo (4 etapas)
- [x] Manter design preto e laranja
- [x] Manter logo do brasão
- [x] Manter responsividade mobile
- [x] Manter ícones do brasão nos dropdowns
- [x] Adaptar campos para formato Discord

### Fase 3: Integração com Discord
- [x] Criar procedure tRPC para enviar ao bot
- [x] Formatar dados conforme esperado pelo bot
- [x] Implementar chamada para https://boteco-production.up.railway.app/enviar
- [x] Adicionar animação de sucesso após envio
- [x] Adicionar tratamento de erro

### Fase 4: Testes e Entrega
- [ ] Testar formulário completo
- [x] Testar envio para Discord (FormData nativo)
- [ ] Verificar formatação no Discord
- [ ] Criar checkpoint final
- [ ] Preparar arquivo para deploy

### Correções de Bugs
- [x] Corrigir envio automático ao colocar horário
- [x] Corrigir navegação para etapa 4
- [x] Manter logo em todas as etapas
- [x] Adicionar ícones e números de cada etapa
- [x] Adicionar brasão ao lado de patentes e prefixos
- [x] Corrigir URL do brasão para imgur (https://i.imgur.com/SQqg1Io.png)
- [x] Adicionar campo "Ocorrências Atendidas" (bos)
- [x] Adicionar campo "Munição"
- [x] Adicionar campo "Bombas"
- [x] Adicionar campo "Relação de Detidos e B.O"
- [x] Adicionar campo "Ações Realizadas pela Equipe"
- [x] Garantir que números zerados sejam enviados corretamente

## Estrutura de Dados Esperada pelo Bot

```javascript
{
  nome_enviou: string,           // Nome do policial encarregado
  patente_enviou: string,        // Patente do policial
  prefixo: string,               // Prefixo da viatura
  chefe_nome: string,            // Nome do chefe de barca
  chefe_patente: string,         // Patente do chefe
  motorista_nome: string,        // Nome do motorista
  motorista_patente: string,     // Patente do motorista
  t3_nome: string,               // Nome do 3º homem
  t3_patente: string,            // Patente do 3º homem
  t4_nome: string,               // Nome do 4º homem
  t4_patente: string,            // Patente do 4º homem
  t5_nome: string,               // Nome do 5º homem
  t5_patente: string,            // Patente do 5º homem
  inicio: string,                // Data/hora início (formato: DD/MM/YYYY HH:MM)
  fim: string,                   // Data/hora fim (formato: DD/MM/YYYY HH:MM)
  drogas: number,                // Quantidade de drogas apreendidas
  armas: number,                 // Quantidade de armamentos apreendidos
  lockpicks: number,             // Quantidade de lockpicks apreendidos
  dinheiro: number,              // Quantidade de dinheiro sujo apreendido
  bos: number,                   // Quantidade de B.O's realizados
  prisoes: number,               // Quantidade de prisões realizadas
  obs: string                    // Observações gerais
}
```

## Prefixos das Viaturas

### TRAIL 23 HUMAITÁ
- 93001, 93002, 93100, 93200, 93121, 93122, 93123, 93157, 93000

### TRAIL 21 HUMAITÁ
- 93001, 93002, 93100, 93200, 93121, 93122, 93123, 93157, 93000

### SPIN
- 3-163, 22-858, 22-871, 22-384, 22-650, BA-046, ESSgt-020, 3-351

## Patentes Disponíveis
- Tenente Coronel
- Major
- Capitão
- 1º Tenente
- 2º Tenente
- Aspirante a Oficial
- Subtenente
- 1º Sargento
- 2º Sargento
- 3º Sargento
- Cabo
- Soldado 1ª Classe
- Soldado 2ª Classe
