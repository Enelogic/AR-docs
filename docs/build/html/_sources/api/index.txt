API Documentatie
=================

Authenticatie
~~~~~~~~~~~~~~

Op dit moment is het enkel mogelijk te autheniceren tegen de API d.m.v. een JWT (Json WebToken).
De JSON Webtoken kan je ophalen door het uit voeren van de volgende HTTP request.

.. http:post:: https://sfu.eu.auth0.com/oauth/ro

  Authenticate and get JWT token.

  :form client_id: JeoeZHZWluOY7xbV2sQ7np3mYLxbBIfa
  :form username: *<gebruikersnaam van gebruiker>*
  :form password: *<wachtwoord van gebruiker>*
  :form connection: AllocationReconcilation
  :form grant_type: password
  :form scope: openid

  **Voorbeeld response**:

   .. sourcecode:: http

      200 OK
      Vary: Accept
      Content-Type: application/json

      {
        "id_token": "eyJ0eXfsETRHSFSDiLCJhbGciOiJIUzI1NiJ9.eyJpc3MifSRHYUKI&&$%gdrger0vIiwic3ViIjoiYXV0aDB8NTdmZGZmYzc0OTM4NmFiOTM5ZjVhN2U1IiwiYXVkIjoiSmVvZVpIWldsdU9ZN3hiVjJzUTducDNtWUx4YkJJZmEiLCJleHAiOjE0NzYzMTAyNzMsImlhdCI6MTQ3NjI3NDI3M30.WiQqdAFFGREGRTMPELOGeSdmkmGK-0QU5wu-MgfsI",
        "access_token": "mqvOoDmDG3kXZJMj",
        "token_type": "bearer"
      }


Endpoints
~~~~~~~~~

Verplichte headers:

- `Authorization`, de waarde hiervan is 'Baerer' + de waarde van *id_token* uit de authenticatie. (bijv. 'Authorization: Baerer 1234567890.ABCDEF.HIJKLMNOP')
- `X-Accept-Version`, de versie van de API die je wil bevragen (laatste versie == 1)

Optionele headers:

- `Accept` (standaard 'application/json'), hiermee bepaal je in welk format je de content terug wil ontvangen. Momenteel is enkel 'application/json' en 'application/xml' ondersteund.

**Alle endpoints van de API zijn terug te vinden op** https://ar.sfu.io/api/doc.
