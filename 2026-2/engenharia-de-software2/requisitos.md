# Requisitos

## 1. Estudo de caso

O sistema a ser desenvolvido deverá permitir a criação, aplicação e análise de pesquisas institucionais, garantindo anonimato dos participantes e organização das respostas por categorias de respondentes.

## 2. Requisitos funcionais

O sistema deverá permitir:

- Manter pesquisas
- Manter categorias de participantes
- Criar questionários por categoria
- Cadastrar perguntas e alternativas
- Gerar códigos anônimos de uso único
- Aplicar questionários com código anônimo e CAPTCHA
- Registrar respostas no banco de dados
- Impedir reutilização dos códigos anônimos
- Monitorar participação em tempo real
- Gerar relatórios estatísticos
- Acessar questionário

## 3. Requisitos não funcionais

- *Usabilidade:* interface web amigável e layout responsivo
- *Segurança:* códigos anônimos protegidos por hash no banco de dados, validação de acesso, proteção contra múltiplas respostas por código anônimo e validação CAPTCHA
- *Performance:* sistema capaz de suportar múltiplos acessos simultâneos
- *Portabilidade:* funcionamento em navegadores modernos

## 4. Requisitos de segurança

- Utilizar HTTPS com certificado SSL/TLS para criptografar a comunicação entre navegador e servidor
- Gerar códigos anônimos e de uso único para acesso aos questionários
- Armazenar somente o hash dos códigos anônimos, sem guardar os originais no banco de dados
- Impedir a reutilização dos códigos após o envio das respostas
- Validar o código anônimo e o CAPTCHA antes da liberação dos questionários
- Proteger o sistema contra múltiplas respostas indevidas
- Realizar backups periódicos do banco de dados
- Garantir a integridade dos arquivos e dados armazenados
- Manter softwares e plugins atualizados para reduzir vulnerabilidades
- Utilizar CAPTCHA para bloquear bots e tráfegos automatizados
- Proteger o domínio e os registros DNS contra acessos não autorizados
- Executar verificações periódicas contra malwares
- Garantir o anonimato dos participantes, sem registrar IPs ou metadados que permitam sua identificação
- Utilizar senhas fortes e autenticação segura para os gestores da pesquisa

### Auditoria

O sistema manterá registros automáticos de eventos para monitorar a integridade dos acessos aos questionários. Sempre que um código anônimo e um CAPTCHA forem validados, ou houver uma tentativa com código inválido, reutilizado ou CAPTCHA incorreto, o sistema registrará apenas a data, a hora e o tipo de evento (sucesso ou falha). Os registros não armazenarão endereço IP, dados do dispositivo nem qualquer informação que permita identificar o respondente.

### Autorização

O gestor da pesquisa possui acesso administrativo, protegido por login e senha, às interfaces de cadastro de questões, geração de códigos anônimos por categoria e visualização de resultados com gráficos e tabelas. O participante acessa a interface inicial com um código anônimo de uso único e conclui a verificação CAPTCHA antes de abrir o questionário de sua categoria. O sistema executa processos internos como validação do código, verificação do CAPTCHA, direcionamento ao questionário da categoria e processamento dos dados.

### Confiabilidade

O sistema utilizará HTTPS com certificado SSL/TLS. Os códigos anônimos serão gerados por método criptograficamente seguro e somente seus hashes serão armazenados. Antes de liberar o questionário, o sistema validará o código e o CAPTCHA. Após o envio das respostas, o código será invalidado automaticamente. O sistema não registrará IPs nem metadados capazes de identificar o dispositivo do respondente.

### Disponibilidade

O sistema será hospedado em uma plataforma web em nuvem, com acesso em qualquer computador mediante código anônimo e validação CAPTCHA. Deverá suportar cerca de 150 acessos simultâneos sem comprometer o desempenho e permanecer disponível 24 horas por dia até o término da pesquisa. Também serão realizados backups periódicos do banco de dados.

### Autenticidade

O acesso dos participantes será controlado por códigos anônimos, individuais e de uso único, vinculados somente à categoria do questionário, sem associação com nome, CPF, e-mail ou outro dado pessoal. O CAPTCHA confirmará que o acesso não foi automatizado. Apenas gestores autorizados acessarão a área administrativa mediante login e senha. Depois do envio das respostas, o código será invalidado.

## 5. Atores

- Gestor da pesquisa
- Participante

## 6. User stories

| Ator | Requisito | O que espera que aconteça? |
| :--- | :--- | :--- |
| Gestor da pesquisa | Manter pesquisas | Acessa a parte do site onde insere o título da pesquisa, o período de duração e as questões. |
| Gestor da pesquisa | Manter categorias de participantes | Define categorias de participantes, permitindo organizar e direcionar questionários específicos para cada grupo. |
| Gestor da pesquisa | Criar questionários por categoria | Gera questionários por categoria, acessíveis com código anônimo de uso único e validação CAPTCHA. |
| Gestor da pesquisa | Cadastrar perguntas e alternativas | Cadastra as perguntas e suas alternativas para que o aluno possa selecionar uma das opções ao responder. |
| Gestor da pesquisa | Gerar códigos anônimos de uso único | Solicita a criação de lotes de códigos anônimos específicos por categoria. |
| Participante | Aplicar questionários com código e CAPTCHA | Informa o código recebido e resolve o CAPTCHA para acessar as perguntas da sua categoria. |
| Sistema | Registrar respostas no banco de dados | O sistema salva os dados de forma segura. |
| Sistema | Impedir reutilização dos códigos | O sistema invalida o código depois do envio das respostas. |
| Gestor da pesquisa | Monitorar participação em tempo real | Vê em tempo real a quantidade de pessoas que acessaram e concluíram a pesquisa. |
| Gestor da pesquisa | Gerar relatórios estatísticos | O sistema processa os dados coletados e apresenta gráficos ou tabelas com os resultados finais. |
| Participante | Acessar questionário | Responde às perguntas designadas a ele e as respostas são salvas no banco de dados. |
| Participante | Solicitar novo código anônimo | Recebe instruções para contatar o gestor e obter outro código, sem quebrar o anonimato. |