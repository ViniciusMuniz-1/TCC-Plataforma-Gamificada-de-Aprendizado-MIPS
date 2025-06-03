# Documento de Visão

**DOCUMENTO DE VISÃO**

1. **Projeto:**
Gamificando o Aprendizado de Assembly: Uma Extensão Educacional para o Simulador MARS

2. **Descrição do problema:**

| O problema de | tornar o aprendizado de Assembly MIPS acessível, atrativo e eficiente para estudantes de computação |
| --- | --- |
| afeta | Estudantes de cursos de Computação, especialmente em disciplinas como Arquitetura de Computadores |
| cujo impacto do problema para o cliente | Dificuldade em compreender e aplicar conceitos de programação em baixo nível, resultando em baixo desempenho, desmotivação e evasão |
| em junção, o problema para os professores é | dificuldade em acompanhar o progresso individual e coletivo dos alunos, além de dependência de correções manuais e demoradas |
| cujo impacto é | comprometimento da qualidade do ensino e sobrecarga de trabalho docente |
| uma boa solução seria | Desenvolver uma plataforma gamificada integrada ao simulador MARS, que ofereça submissão e correção automática de exercícios, feedback em tempo real, recompensas e ranking de usuários. A solução promoverá motivação, prática constante e acompanhamento mais eficaz do desempenho dos alunos. |

3. **Descrição dos usuários:**

| Nome       | Descrição                                                                   | Responsabilidade                                                                 |
|------------|-----------------------------------------------------------------------------|----------------------------------------------------------------------------------|
| Estudante  | Usuário que acessa a plataforma para resolver desafios em Assembly MIPS     | Submete códigos, recebe feedback, acompanha progresso, participa do ranking     |
| Professor  | Usuário com acesso a estatísticas e relatórios de desempenho dos alunos     | Acompanha evolução, propõe exercícios, utiliza a ferramenta como apoio didático |
| Administrador | Responsável técnico pela manutenção da plataforma                       | Gerencia usuários, desafios, rankings e métricas do sistema                     |

4. **Descrição do ambiente dos usuários:**

- A plataforma será acessada através da interface do MARS, ou via uma interface adicional, compatível com desktop (inicialmente);
- Requer Java instalado e acesso ao simulador MARS;
- Não exige conexão contínua com a internet na versão offline, mas poderá ser expandida para versão online;
- Estudantes geralmente a utilizarão em laboratórios de informática, notebooks pessoais ou ambientes acadêmicos controlados.

5. **Principais necessidades dos usuários:**

- Praticar programação Assembly com orientação: Exercícios interativos e desafios progressivos;
- Receber feedback imediato: Saber onde errou e como melhorar;
- Se motivar através da gamificação: Sistema de pontos, conquistas e rankings;
- Visualizar evolução pessoal: Acompanhamento de progresso e estatísticas;
- Acompanhar alunos (para professores): Visualizar desempenho, participação e dificuldades dos alunos.

6. **Alternativas concorrentes:**

| Plataforma               | Pontos Fortes                                          | Pontos Fracos                                                   |
|--------------------------|--------------------------------------------------------|------------------------------------------------------------------|
| MARS (original)          | Robusto, amplamente utilizado, simula com precisão     | Não possui correção automática nem recursos educacionais/gamificados |
| Beecrowd                 | Correção automática, desafios variados                 | Não suporta Assembly nem integra com MARS                        |
| Codewars, HackerRank, LeetCode | Experiência gamificada, rankings                | Não oferecem suporte a Assembly MIPS                             |
| Simuladores concorrentes (QtSPIM, xMIPS) | Simulação MIPS                    | Sem gamificação ou correção automatizada                         |

7. **Visão geral do produto:**

A extensão será um complemento do simulador MARS, focada em:

- Submissão de códigos para resolução de exercícios propostos;
- Correção automática com base em testes internos;
- Feedback em tempo real com mensagens de erro ou sugestões;
- Sistema de pontos, medalhas e conquistas conforme o progresso;
- Ranking entre usuários;
- Perfis com histórico de atividades e estatísticas individuais.

8. **Requisitos FUNCIONAIS:**

| Código | Nome                | Descrição                                                                 |
|--------|---------------------|---------------------------------------------------------------------------|
| RF01   | Submissão de exercícios | Permite que o aluno envie soluções em Assembly MIPS                     |
| RF02   | Correção automática     | Compara a saída do código com o resultado esperado                      |
| RF03   | Feedback imediato       | Exibe informações úteis ao aluno sobre seu desempenho                   |
| RF04   | Sistema de pontuação    | Atribui pontos conforme o desempenho nos exercícios                     |
| RF05   | Ranking de usuários     | Lista usuários ordenados por pontuação ou progresso                     |
| RF06   | Histórico do usuário    | Mostra os exercícios feitos, erros comuns, tempo médio etc.             |
| RF07   | Gerenciar desafios      | Permite ao administrador/professor criar e editar exercícios            |
| RF08   | Estatísticas do aluno   | Geração de relatórios com desempenho individual ou coletivo             |

9. **Requisitos NÃO-FUNCIONAIS:**

| Código  | Nome                      | Descrição                                                                 | Categoria ISO 25010                       | Classificação | Métrica                                                                 |
|---------|---------------------------|---------------------------------------------------------------------------|------------------------------------------|----------------|-------------------------------------------------------------------------|
| RNF01   | Compatibilidade com MARS  | O sistema deve funcionar como extensão nativa ou ser compatível com o simulador MARS. | Portabilidade → Compatibilidade           | Obrigatório    | Executar o sistema no MARS sem erro em 100% dos testes.                |
| RNF02   | Tempo de resposta         | O sistema deve apresentar o feedback da correção ao usuário em até 3 segundos após o envio. | Desempenho → Tempo de resposta             | Obrigatório    | Medir tempo entre envio da resposta e exibição do feedback. **Meta**: ≤ 3s para 98% dos casos. |
| RNF03   | Interface amigável        | Interface gráfica intuitiva e acessível a usuários iniciantes.           | Usabilidade → Apreensibilidade, Operacionalidade | Obrigatório    | Testes com iniciantes. **Meta**: 80% dos usuários usam sem ajuda externa. |
| RNF04   | Persistência local de dados | O sistema deve armazenar dados localmente, mesmo sem internet.            | Confiabilidade → Tolerância a falhas, Recuperabilidade | Opcional       | Simular desconexão e reinício. **Meta**: dados preservados em 100% dos testes. |
| RNF05   | Modularidade do código    | Estrutura modular para facilitar manutenção e extensões futuras.         | Manutenibilidade → Modularidade, Analisabilidade | Obrigatório    | Análise de acoplamento/coesão. Ferramentas como SonarQube.             |
| RNF06   | Segurança dos dados       | Proteger dados do usuário contra acesso não autorizado.                  | Segurança → Confidencialidade              | Obrigatório    | Verificar criptografia e controle de acesso.                           |
| RNF07   | Facilidade de instalação  | Instalação simples e rápida, sem dependências complexas.                | Portabilidade → Instalabilidade            | Obrigatório    | Tempo de instalação ≤ 5 min em ambiente limpo.                         |