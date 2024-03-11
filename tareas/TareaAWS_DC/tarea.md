### Entrega un Readme con la explicación de como ejecutar la aplicación en python para actualizar un mensaje.

### Explica como se crea un virtual environment y como se configura la capa de la funciones.


## 1. Abrimos Pycharm en nuestro equipo y escribimos el siguiente codigo:

            # importamos las librerias necesarias
            from discord_webhook import DiscordWebhook, DiscordEmbed
            import json
            import requests

            # Creamos el webhook y el embed, sustituyendo el enlace al webhook por el que hayamos creado en Discord
            webhook = DiscordWebhook(url="enlace al webhook")

            # Creamos el embed
            embed = DiscordEmbed(
                # titulo, descripcion y color del embed
                title="Taco Love",
                description="Tu taquito ya está!",
                color="03b2f8")

            # Añadimos la imagen del taco al mensaje
            embed.set_image(url="https://cdn.dribbble.com/users/545781/screenshots/3157610/happy-taco.jpg")
            # Añadimos el embed al webhook
            webhook.add_embed(embed)
            # Ejecutamos el webhook, enviando el mensaje a Discord
            webhook.execute()



            def lambda_handler(event, context):
                # TODO implement
                return {
                    'statusCode': 200,
                    'body': json.dumps('Hello from Discord Lambda!')
    }

#


## 2. Ejecutamos el comando "source venv/bin/activate" para activar el entorno virtual.

![VENV](https://github.com/sarald22/SRI/blob/main/tareas/TareaAWS_DC/img/venv.png)


#

## 3. instalamos el paquete de webhooks de discord; puede ser por terminal o por interfaz.

- Por interfaz sería con el comando:

            pip install discord-webhooks


- Por interfaz sería yendo a Python Pakcges, buscando el paquete y dándole a instalar:

![instalacion](https://github.com/sarald22/SRI/blob/main/tareas/TareaAWS_DC/img/dcinstall.png)

