Projeto 8 — Diretrizes de Nomenclatura de Código


Contexto
O **Projeto 8** documenta um conjunto de **diretrizes de nomenclatura e organização de código** que servem como boas práticas para manter consistência, legibilidade e manutenibilidade em projetos de software, especialmente em testes automatizados.
 Diretrizes
Variáveis
- Use **`snake_case`** para nomear variáveis.  
- Os nomes devem ser **descritivos**, refletindo claramente a finalidade da variável.  
Exemplo:
```python
user_id = 123
total_price = 49.90
Constantes
Sempre em MAIÚSCULAS.


Úteis para valores fixos ou que não devem ser alterados.






Exemplo:
python
MAX_RETRY = 3
BASE_URL = "https://api.exemplo.com"
Comentários
Utilize comentários para explicar blocos importantes de código, regras de negócio ou decisões técnicas.


Evite comentários redundantes que apenas repetem o que já está explícito no código.


Exemplo:


python


Verifica se o usuário está autenticado antes de continuar
if not user.is_authenticated:
    raise PermissionError("Usuário não autenticado")
Organização do Código
Estruture o código de forma modular.


Crie funções e classes reutilizáveis, importando-os apenas onde necessário.


Evite duplicação de código.
Python


 helpers/math_utils.py
def calcular_media(valores):
    return sum(valores) / len(valores)


 tests/test_calculos.py
from helpers.math_utils import calcular_media


def test_calculo_media():
    assert calcular_media([2, 4, 6]) == 4
Funções de Espera
Evite waits desnecessários (time.sleep) que tornam a execução mais lenta.


Prefira esperas inteligentes (ex.: wait explícito em testes de UI).
Exemplo ruim:


python
time.sleep(5)  # Espera fixa e desnecessária
Exemplo correto:
python
# Espera até o elemento aparecer (máximo de 5 segundos)
page.wait_for_selector("#login-button", timeout=5000)
Convenção de Testes
Todos os testes devem seguir a convenção:


O nome começa com test_


A descrição do cenário é clara e objetiva


O resumo do teste deve refletir exatamente o que está sendo validado.
Exemplo:
python


def test_login_com_credenciais_validas():
  Cenário: usuário faz login com credenciais corretas
    assert login("user", "password") == "Login realizado com sucesso"
Conclusão
Essas diretrizes ajudam a manter o código limpo, legível e sustentável.
Aplicar essas práticas no dia a dia melhora a colaboração entre equipes e reduz a probabilidade de erros em projetos de software.
