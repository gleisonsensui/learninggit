# Tipos de ramos e regras estabelecidas no gitflow

## Versionamento semantico
Dado um número de versão MAJOR.MINOR.PATCH, incremente a:

*   versão Maior(MAJOR): quando fizer mudanças incompatíveis na API,
*   versão Menor(MINOR): quando adicionar funcionalidades mantendo compatibilidade, e
*   versão de Correção(PATCH): quando corrigir falhas mantendo compatibilidade.
Rótulos adicionais para pré-lançamento(pre-release) e metadados de construção(build) estão disponíveis como extensão ao formato MAJOR.MINOR.PATCH.
Fonte: https://semver.org/lang/pt-BR/

## Branch master
*   Em qual repositorio está?
    *   Origin (central)
*   O que contem?
    *   O que está em produção. Tambem conhecido como trunk
*   Padrão de nome:
    *   N/A
*   Tempo de vida
    *   Infinito
*   Pode se ramificar a partir da branch:
    *   N/A
*   Pode se fundir com a branch:
    *   N/A
*   Exemplo de tag:
    *   1.1.14: MAJOR.MINOR.PATCH
*   Observação:
    *   Cada fusão gerará uma nova versão, que pode ou não ser uma de incremento MAJOR. Mas, provavelmente, sempre irá gerar um incremento em niveis     MINOR e PATCH, devido a hotfix ou release e novas funcionalidades que não ocasionam impacto sobre a arquitetura, compatibilidade ou estrutura do sistema.

## Branch hotfix
*   Em qual repositorio está?
    *   local
*   O que contem?
    *   Correção de um bug critico, que não pode esperarf pela proxima release
*   Padrão de nome:
    *   hotfix-*
*   Tempo de vida
    *   Até que esteja pronto para ser liberado para produção.
*   Pode se ramificar a partir da branch:
    *   master
*   Pode se fundir com a branch:
    *   master; develop; release
*   Exemplo de tag:
    *   1.1.15: MAJOR.MINOR.PATCH:hotfix
*   Observação:
    *   Dever ser fundido primeiro com a master e então com a develop

## Branch release
*   Em qual repositorio está?
    *   Origin (central)
*   O que contem?
    *   O que irá para produção, fruto de incremento de iterações
*   Padrão de nome:
    *   release-*
*   Tempo de vida
    *   Até que esteja pronto para ser liberado para produção
*   Pode se ramificar a partir da branch:
    *   develop    
*   Pode se fundir com a branch:
    *   master e develop
*   Exemplo de tag:
    *   1.2: MAJOR.MINOR:release
*   Observação:
    *   Deve ser fundido primeiro com a master e então com a develop

## Branch develop
*   Em qual repositorio está?
    *   origin (central)
*   O que contem?
    *   O que irá para a proxima release
*   Padrão de nome:
    *   N/A
*   Tempo de vida
    *   Infinito
*   Pode se ramificar a partir da branch:
    *   master
*   Pode se fundir com a branch:
    *   feature; develop e release
*   Exemplo de tag:
    *   N/A
*   Observação:
    *   N/A

## Branch feature
*   Em qual repositorio está?
    *   local
*   O que contem?
    *   Uma nova implementação para a proxima ou para uma release futura.
*   Padrão de nome:
    *   livre, exceto master, develop, release-*, hotfix-*
*   Tempo de vida
    *   Enquanto estiver em desenvolvimento
*   Pode se ramificar a partir da branch:
    *   develop
*   Pode se fundir com a branch:
    *   develop
*   Exemplo de tag:
    *   N/A
*   Observação:
    *   Um ramo para cada nova implementação (feature)