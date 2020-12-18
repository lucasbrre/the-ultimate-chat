# the-ultimate-chat
Création d'un chat – The ultime chat - et réaliser le graphisme minimum par groupe de deux, voici les besoins de votre solution finale

<!DOCTYPE html>
    <html lang="fr">
        <head>
            <meta charset="utf-8">
            <title>The ultime CHAT</title>
            <link rel="stylesheet" href="style.css">
        </head>

        <body>

        <!-- Demander un pseudo à l'utilisateur --> 
        <!-- Interdire les caractères spéciaux et les chiffres dans le pseudo -->
            <div id="divpseudo">
                <label class="pseudo" for="pseudo">Pseudo :</label> 
                <input type="text" name="pseudo" id="pseudo" value="Rentrez votre pseudo" required pattern="[A-Za-z]{0,50}"/> 
            </div>

        <!-- Pouvoir envoyer des messages --> 
    
        <div>
            <label for="message">Message :</label> 
            <input type="text" name="message" id="message" value="Envoyez votre message 👋" required />
        </div>

        <p>
            <input type="submit" value="Envoyer" id="envoyer" onclick="recuperation()" />
        </p>

        <!-- Chaque message est accompagné de l'heure d'envoi -->
        
        <div id="monhorloge"></div>
        <div id="content"></div>

        <script>

        // Demander un pseudo à l'utilisateur
        // Pouvoir envoyer des messages 

            function recuperation ()
            {
                //console.log('test')
                var pseudo = document.getElementById("pseudo").value;
                var message = document.getElementById("message").value;
                var dt=new Date();

                //console.log(pseudo)
                //console.log(message)

                var content = document.getElementById("content").innerHTML;
                var time = dt.getHours()+":"+dt.getMinutes()+":"+dt.getSeconds();
                var line = '<p>'+time+' '+pseudo+' '+message+'</p>';

                document.getElementById("content").innerHTML=content+line;

            }

        // Chaque message est accompagné de l'heure d'envoi

            function horloge() 
            {
                var dt=new Date();
                document.getElementById("monhorloge").innerHTML=""+dt.getHours()+":"+dt.getMinutes()+":"+dt.getSeconds()+" Le "+dt.getDate()+'/'+(dt.getMonth()+1)+'/'+dt.getFullYear();
            }

                var timer=setInterval("horloge()", 250);
        
        // Permettre à l'utilisateur de changer la couleur et la taille de ses messages

                const message = 'merde';'oups'
                const replaceWith = '****';'@&#$!';'& #$*';

                const message = '****';'@&#$!';'& #$*'.replaceAll(message, replaceWith);
                result;

        // Pouvoir recevoir des messages (optionnel - AJAX) 

 

        // Remplacer les insultes par des caractères spéciaux de façon aléatoire (& #$*) 

 

        // Pouvoir quitter le chat en se déconnectant sans quitter la page

 

        // Affichage de la date et de l'heure actuelles 
            </script>

        </body>
    </html> 
