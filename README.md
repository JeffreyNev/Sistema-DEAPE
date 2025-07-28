# Sistema de Gerenciamento de Servidores e Cursos - ICMBio (ACADEBio)

Este projeto é uma aplicação web desenvolvida para o ICMBio (Instituto Chico Mendes de Conservação da Biodiversidade) com o objetivo de gerenciar informações sobre servidores e os cursos/capacitações em que participam, com foco no controle da Gratificação por Encargo de Curso ou Concurso (GECC).

A aplicação permite o cadastro, edição, exclusão e consulta de registros de servidores e cursos, além de oferecer funcionalidades de relatórios e um dashboard para visualização de estatísticas relacionadas à GECC.

## Funcionalidades Principais

*   **Cadastro e Gerenciamento de Servidores:**
    *   Registro de dados pessoais e funcionais do servidor (Nome, Matrícula SIAPE, CPF, Cargo, Unidade, Chefia, Processo SEI).
    *   Informações sobre status (Portariado, Teletrabalho, Time Volante).
    *   Detalhes sobre GECC (Status, Horas Solicitadas, Valor Recebido, FOPAG).
    *   Controle do PGD (Programa de Gestão de Desempenho) e Declaração de Compensação.
*   **Cadastro e Gerenciamento de Cursos/Capacitações:**
    *   Registro de informações do curso (Nome, Processo SEI, Função Exercida pelo servidor, Modalidade, Local, Período, Carga Horária, Status).
    *   Campo para observações.
*   **Pesquisa e Navegação:**
    *   Pesquisa por nome do servidor ou nome da capacitação.
    *   Navegação sequencial entre os registros diretamente no formulário.
*   **Relatórios:**
    *   **Relatórios PDF:** Geração de relatórios detalhados em formato PDF.
    *   **Relatório Anual (2025):** Consulta e exportação em PDF de registros específicos do ano de 2025.
    *   **Relatório Simplificado:** Exportação em PDF de um resumo com colunas selecionadas.
*   **Dashboard e Estatísticas:**
    *   Visualização gráfica do total pago de GECC por servidor.
    *   Filtros por FOPAG e Status GECC no dashboard.
    *   Exportação do gráfico do dashboard como imagem.
*   **Painel Geral de Servidores:**
    *   Modal com filtros avançados para consulta de servidores (Nome, Portariado, Teletrabalho, Time Volante, Status PGD).
    *   Exportação dos resultados filtrados em PDF.
*   **Gerenciamento de Dados:**
    *   **Exportação/Importação de Dados (.json):** Permite fazer backup de todos os registros e restaurá-los em outro navegador/computador.
    *   **Exportação de Registros do Dia (.csv):** Gera um arquivo CSV com os registros salvos no dia corrente.
    *   **Exclusão de Registros:** Permite excluir um registro individualmente ou todos os registros (com confirmação por senha).
*   **Autenticação:**
    *   Acesso ao formulário principal protegido por senha.

## Tecnologias Utilizadas

*   **Frontend:**
    *   [Next.js](https://nextjs.org/) (App Router)
    *   [React](https://reactjs.org/)
    *   [TypeScript](https://www.typescriptlang.org/)
*   **UI e Estilização:**
    *   [ShadCN UI](https://ui.shadcn.com/) (Componentes)
    *   [Tailwind CSS](https://tailwindcss.com/)
    *   [Lucide React](https://lucide.dev/) (Ícones)
*   **Manipulação de Datas:**
    *   [date-fns](https://date-fns.org/)
*   **Geração de PDF:**
    *   [jsPDF](https://parall.ax/products/jspdf)
    *   [html2canvas](https://html2canvas.hertzen.com/)
*   **Armazenamento de Dados (Local):**
    *   `localStorage` do navegador.
*   **Outras Bibliotecas:**
    *   `recharts` (para gráficos no dashboard)

## Configuração e Execução do Projeto

1.  **Clone o repositório (se aplicável):**
    ```bash
    git clone <url-do-repositorio>
    cd <nome-da-pasta-do-projeto>
    ```

2.  **Instale as dependências:**
    ```bash
    npm install
    # ou
    yarn install
    # ou
    pnpm install
    ```

3.  **Execute o servidor de desenvolvimento:**
    ```bash
    npm run dev
    ```
    Por padrão, o projeto estará acessível em `http://localhost:9003` ou na porta especificada no script `dev` do `package.json`.

4.  **Acesso ao Formulário:**
    A senha padrão para acesso ao formulário é: `senha@1`.

## Estrutura do Projeto (Principais Pastas)

*   `/src/app`: Contém as páginas da aplicação (App Router do Next.js).
    *   `/src/app/formulario`: Página principal de cadastro e gerenciamento.
    *   `/src/app/relatorios-gecc`: Página para visualização e exportação de relatórios de GECC.
    *   `/src/app/graficos-estatisticas`: Página do dashboard com estatísticas.
    *   `/src/app/api`: Rotas de API (ex: autenticação).
*   `/src/components`: Componentes React reutilizáveis.
    *   `/src/components/ui`: Componentes da biblioteca ShadCN UI.
    *   `/src/components/dashboard`: Componentes específicos do dashboard.
    *   `/src/components/relatorios`: Componentes específicos para relatórios.
    *   `/src/components/paineis`: Componentes para painéis de consulta.
*   `/src/hooks`: Hooks React customizados (ex: `useToast`, `useMobile`).
*   `/src/lib`: Utilitários e configurações (ex: `utils.ts`).
*   `/src/services`: Lógica de serviços (ex: `auth.ts`).
*   `/public`: Arquivos estáticos.

## Considerações

*   **Persistência de Dados:** Atualmente, todos os dados dos registros são armazenados no `localStorage` do navegador. Isso significa que os dados são locais para cada navegador e não são compartilhados entre diferentes computadores ou usuários, a menos que a funcionalidade de exportação/importação de JSON seja utilizada.
*   **Segurança da Senha:** A senha de acesso está codificada no arquivo `src/services/auth.ts`. Para um ambiente de produção, um sistema de autenticação mais robusto seria necessário.

---

Este README fornece uma visão geral do projeto. Para mais detalhes sobre componentes específicos ou fluxos de dados, consulte o código-fonte correspondente.
