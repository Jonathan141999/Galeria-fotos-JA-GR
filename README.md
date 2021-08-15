# Galeria-fotos-JA-GR

INTEGRANTES: Jonathan Alquinga y Guillermo Rivera

DETALLE DEL PROYECTO:

El proyecto consiste en desarrollar una aplicación en react con ionic que permita tomar fotografías en un dispositivo móvil, de tal manera que estas
se almacenen de forma permanente en el dispositivo, dicha aplicación es híbrida sin embargo se hace uso de capacitor para que tenga una funcionalidad 
nativa, a continuación se muestran los pasos:

1.- Creación del proyecto por medio de líneas de comando y agregando capacitor:

/*      ionic start photo-gallery tabs --type=react --capacitor      */

2.- Ac continuación, se instalan pluggins de capacitor así como la API de la cámara para poder mejorar la experiencia de usuario y el correcto funcionamiento
de la App, los comandos son:

/*      npm install @capacitor/camera @capacitor/storage @capacitor/filesystem      */ 
/*      npm install @ionic/pwa-elements       */

3.- Lo que le sigue es importar las librerías dentro del proyecto:

/*
import { defineCustomElements } from '@ionic/pwa-elements/loader';

// Call the element loader after the platform has been bootstrapped
defineCustomElements(window);
*/

4.- Para comprobar el funcionamiento de la aplicación se realiza la ejecución  de la misma, por lo cual con (ionic serve) dentro del terminal del proyecto bastará.

5.- Sin embargo no se ha trabajado la parte de la interfaz gráfica por lo cual se debe incorporar las etiquetas necesarias mejorar la experiencia del usuario, de la
siguiente manera:

/*
<IonPage>
  <IonHeader>
    <IonToolbar>
      <IonTitle>Tab 2</IonTitle>
    </IonToolbar>
  </IonHeader>
  <IonContent>
  <!-- some filler -->
  </IonContent>
</IonPage>
*/

6.- Debido a que se utilizan componentes nuevos, son necesarios importarlos, así como las librerías de la cámara, por lo cual en la parte superior del documento html que nos 
encontramos editando se debe importar lo siguiente:

/*
import { camera, trash, close } from 'ionicons/icons';
import { IonContent, IonHeader, IonPage, IonTitle, IonToolbar,
         IonFab, IonFabButton, IonIcon, IonGrid, IonRow,
         IonCol, IonImg, IonActionSheet } from '@ionic/react';
*/
         
7.- Como se usar un botón de acción flotante para el llamado de la función que realiza las acciones de tomado de la fotografía es necesario incoporarlo en la etiqueta
del documento html actual, de la siguiente manera:

/*
<IonContent>
  <IonFab vertical="bottom" horizontal="center" slot="fixed">
    <IonFabButton onClick={() => takePhoto()}>
      <IonIcon icon={camera}></IonIcon>
    </IonFabButton>
  </IonFab>
</IonContent>
*/

8.- A continuación, se modifica el documento src/App.tsx  para agregar la siguiente importación:

/*
import { images, square, triangle } from 'ionicons/icons';
*/

Dicha importación permite realizar las acciones de la cámara.

9.- Como se trabaja con un proyecto realizado con pestañas, se modifica las etiquetas para agregar el ícono de la cámara de tal manera que quede posicionada
de forma central, de la siguiente manera:

/*
<IonTabButton tab="tab2" href="/tab2">
  <IonIcon icon={images} />
  <IonLabel>Photos</IonLabel>
</IonTabButton>
*/

10.- A continuación se prueba el funcionamiento de manera nativa, de tal forma que se general el apk, se emulación de la aplicación o la instalación en un 
dispositivo para comprobar el correcto funcionamiento.

![image](https://user-images.githubusercontent.com/66144899/129464058-2a0b1dd6-71bb-4ef5-87be-f8d13a8b5291.png)


