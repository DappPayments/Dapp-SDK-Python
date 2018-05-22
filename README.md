# Dapp SDK Python #

[Dapp](https://dapp.mx) es una plataforma de pagos, enfocada en la seguridad de sus usuarios. Este SDK es la forma más fácil de integrar [Dapp](https://dapp.mx) en tu desarrollo python. Para obtener tu *merchant_id* y *api_key* entra en tu [dashboard](https://dapp.mx/dashboard) y selecciona la opción "developer" del menú lateral.

**Instalar**

```sh
pip install dappmx
```
o
```sh
easy_install dappmx
```

**Configurar**
```python
import dappmx
dappmx.merchant_id = '274f2f9f-1728-4d3d-865d-b6c40199e428'
dappmx.api_key = '51f085d3-8af4-4aca-a192-f6581a09f66f'
dappmx.is_sandbox = True
```

**Códigos Cobro**
```python
# Crear código dapp
dapp_code = dappmx.DappCode.create({
    "amount": "1.00",
    "description": "prueba python",
    "reference": "referencia de mi app 2213",
})

# Consultar código dapp
dapp_code = dappmx.DappCode.retreive("_kilR1UM") 

# Obtener el pago de un código dapp
dapp_code.payment()
```

**Tarjetas**
```python
# Crear tarjeta
card = dappmx.Card.create({
    "card_number": "4111111111111111",
    "cardholder": "Javier Torres",
    "cvv": "123",
    "exp_month": "12",
    "exp_year": "22",
    "email": "javier.torres@test.com",
    "phone_number": "4422222222"
})

# Consultar tarjeta
card = dappmx.Card.retreive("890d5b17-6551-40ac-a583-46cf7da791bc")

```

**Pagos**
```python
# Crear un pago
payment = dappmx.Payment.create({
    "amount": "33.00",
    "description": "Test",
    "reference": "referencia de mi app 123",
    "card": "890d5b17-6551-40ac-a583-46cf7da791bc",
})

# Consultar un pago
payment = dappmx.Payment.retreive("83eeec01-869c-4d80-a7c8-5109cd85a8ae")

# Reembolsar un pago
payment.refund()

```

## Licencia

[MIT License](LICENSE.txt)
