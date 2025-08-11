# Acerca de los frameworks.
## ¿Qué es un framework?

Lo definimos como el molde que utilizan los programadores para agilizar procesos reutilizar herramientas y desarrollar 
software de forma rápida y sin sacrificar calidad. 
Normalmente antes de iniciar un proyecto, los desarrolladores de software eligen sobre qué framework van a trabajar.
Es una buena práctica definir el framework a utilizar y no sólo por elegir uno, es decir, no cualquiera puede ser 
útil porque cada uno tiene sus fortalezas y sus debilidades.
Es importante resaltar que el término framework no se usa sólo cuando se va a desarrollar software, también se utiliza 
para estrategias de marketing, así que no debe confundirse.

## Frameworks en específico (MVC, SPA).
### MVC
Como uno de las arquitecturas más famosas tenemos el MVC (Modelo-Vista-Controlador) el cuál
a grandes rasgos se encarga de separar el proyecto en desarrollo, teniendo la lógica de la
aplicación de un lado y la lógica de la vista (como lo puede ser la GUI). Muchos de los
frameworks actuales utilizan esta arquitectura.
### SPA
Por sus siglas en inglés single-Page application. Esta arquitectura es mayormente utilizada
para el desarrollo web, al contrario que MVC que su uso se extiende en el desarrollo tanto de web como de escritorio. 
Es una arquitectura que está pensanda para mejorar la experiencia de usuario
dandole un uso más fluido al uso de la aplicación desarrollada.
El hecho de que no se perciva un tipo de recarga en la página no significa que no se está actualizando la página o 
viajando hacia otra dirección web del mismo sitio, todo lo contrario podemos encontrar incluso distintas vistas 
para cada apartado equivalentes a las páginas que componen una MPA(Multi Page Application).

### Ejemplo de la arquitectura MVC

El modelo vista controlador esta separado por 3 capaz, la vista, el controlador y el modelo, como su nombre lo dice.
A grandes rasgos la vista toma las acciones del usuario y las envia al controlador, donde este decide que hacer
con la acción y al enviarla al modelo, este le responde qué hacer con esa petición del usuario. Podemos ver al controlador
como un intermediario entre el **backend y el frontend**

De esta forma tenemos que la estructura del proyecto en general es la siguiente:
- sources
    - modelo
    - vista
    - controlador


Un ejemplo de código sería el siguiente:


public class TextElementModel extends AbstractModel
{

    private String text;
    private Font font;
    private Integer x;
    private Integer y;
    private Integer opacity;
    private Integer rotation;


    /**
     * Provides the means to set or reset the model to
     * a default state
     */
    public void initDefault() {

        setOpacity(89);
        setRotation(0);
        setText("Sample Text");
        setFont(new Font("Arial", Font.BOLD, 24));
        setX(50);
        setY(50);

    }

    //  Accessors


    public String getText() {
        return text;
    }

    public void setText(String text) {

        String oldText = this.text;
        this.text = text;

        firePropertyChange(
            DefaultController.ELEMENT_TEXT_PROPERTY,
            oldText, text);
    }

    public Font getFont() {
        return font;
    }

    public void setFont(Font font) {

        Font oldFont = this.font;
        this.font = font;

        firePropertyChange(
            DefaultController.ELEMENT_FONT_PROPERTY,
            oldFont, font);
    }

    //  The remaining accessors for properties are omitted.

}


### Comparación entre MVC y SPA

Como pudimos ver anteriormente MVC tiene un enfoque más de separar, esperar una petición y obtener una respuesta, a partir de eso generar una relación con el usuario de interacción.
En cambio el SPA tiene un enfoque más de mostrar fluides, que el usuario se sienta lo más cómodo posible.


# Control de versiones y trabajo colaborativo
Se le llama control de versiones a la gestión de los diversos cambios que se realizan sobre algún producto, esto con el fin de
mantener un tipo de bitácora sobre dichos cambios. En desarrollo de software, estos son escenciales porque facilitan la administración de distintas versiones
del producto desarrollado y si se produce algún error durante la ejecución de algún
programa informático, se puede volver a una versión anterior sin errores mientras se resuelve el problema de la versión actual

## Commit, branch, merge, pull request.
Para entender el tema de control de versiones es importante tener bien definidos
los significados de lo mencionado anteriormente.
- **Commit**: Se refiere a la acción de generar algún cambio válido en una de las ramas generadas durante el desarrollo de un proyecto.
- **Branch**: Branch es una versión del código fuente que trabaja en paralelo a la versión original, facilitando hacer pruebas e implementar nuevas funcionalidades en un proyecto sin afectar el principal.
- **Merge**: Merge es la acción de combinar dos **Branches** de un proyecto en una sola.
- **Pull request**: Se refiere a la solicitud que se hace(a algún administrador) de fusionar dos branches en una sola.

## Flujos de trabajo comunes.
Los flujos de trabajo comunes se refieren a la forma de organización para el ciclo de vida de un proyecto. Para esto existen muchos flujos de trabajo como lo son Git Flow, Trunk- based, feature branches.
En principio Git Flow fue muy utilizado para gestionar las ramas de git, sin embargo en la actualidad, ha sido remplazado con trunk-based. 
Trunk-based es una práctica de desarrollo donde las involucrados en mantener el software hacen
actualizaciones pequeñas a una rama principal facilitando la fase de integración. De esta forma se eleva el rendimiento del equipo de trabajo.

## ¿Cómo usar Git en un proyecto?

## Herramientas recomendadas.

Sin duda alguna hay muchisimas herramientas para desarrollar software colaborativamente y muchas de ellas tienen
características únicas, sin embargo en la actualidad, Github es de lejos la más famosa de todas
Es muy completa, simple de utilizar y también muy intuitiva y agradable a la vista, pero sin duda lo completa que es, es su punto más fuerte.

# Autenticación y seguridad moderna.

## Algunos conceptos...

La seguridad es algo escencial dentro del mundo de desarrollo por eso es importante tener 
bien claro los conceptos.
Primero tenemos la autenticación que podemos definirla como el proceso de confirmación que tiene que realizar algún ente (persona, empresa, etc...)
para poder acceder a los servicios de y recursos de una organización. Muy relacionado a este término, también tenemos la autorización, que es
la comprobación que los usuarios si tengan el permiso para acceder al sistema.
También tenemos los tokens de autenticación que son los encargados de mantener abierta una sesión mientras no se cierre el sitio web o se cierre 
la sesión. Son como los boletos a una actividad, mientras lo tengas puedes estar dentro.
Los JSON Web Token (JWT) son tokens que intercambian el cliente y el sitio web para verificar la autenticidad de datos.
Hay 2 formatos para representar los JWT, los JWS y los JWE, sin embargo los JWE 
son los más utilizados porque son los más seguros encriptando la información del contenido del JWT.
Finalmente tenemos el término OAuth que se refiere a un protocolo de autorización que permite
dar acceso a un conjunto de recursos alojados en otro sitio web en nombre de un usuario sin exponerlo.

## Buenas prácticas en seguridad web.
Para desarrollar páginas y sitios web es escencial mantener un estandar de seguridad, por eso
una de las mejores prácticas que se pueden tener es planificar desde el principio los protocolos de seguridad que tendrá lo que se está desarrollando.
También es escencial que sea probada rigurosamente por terceros y que pase excitosamente por auditorías estrictas.
El cifrado de datos confidenciales es de suma importancia para prevenir el robo de datos sensibles para el usuario y de esta forma sumar más
confianza tanto como desarrolladores como para usuarios del sitio/página web.
Podemos mencionar también que los desarrolladores de software debemos de utilizar aquellos algoritmos de seguridad ya
más que probados de que funcionan y también que proveen un alto nivel de seguridad.
Esto nos ayuda a mantener estándares del mercado.

## Aplicaciones en la actualidad.
Actualmente muchas páginas web y aplicaciones usan las herramientas mencionadas anteriormente para mantenerse seguras.
Con la cantidad de información que hay hoy en día cualquier persona con conocimientos puede vulneral una app que no cumpla con ciertos
estándares de seguridad, por eso todas aquellas apps exitosas de la actualidad son robustas a nivel de protección.

## Gestores de contenido desacoplado (Headless CMS).

### Headless CMS vs CMS Tradicional.
CMS significa en español sistema de administración de contenido y es a grandes rasgos un repositorio de contenido que entrega contenido a cualquier frontend.
Anteriormente el backend y el frontend estaban estrechamente relacionados, la separación de proyectos era prácticamente nula, además, los contenidos tomados por el frontend se
entregaban con cierto formato específico que reducía la posibilidad de generar algún tipo de cambios, eso era el CMS tradicional.
Pasando el tiempo se fue observando que se tenía que evolucionar, por eso se desacoplaron el backend y el frontend
y de esta forma se separa la gestión de contenidos, entonces los desarrolladores pudieron usar sus tecnologías preferidas qeu son más fáciles de mantener.

## Arquitectura basada en APIs.
En un sistema de software actual ya casi no existen aplicaciones o páginas en las cuales una sola API se encargue de gestionar
todo lo que sucede ahí, no, ahora la arquitectura basada en APIs define que muchas de las peticiones que envía un cliente
son respondidas por muchas APIs diferentes, es decir, si yo quiero obtener la información de un producto por ejemplo, entonces una API se encarga de eso, si quiero pagar un producto, otra API hace el trabajo de esa petición.
Esto aumenta aún más la separación entre funcionalidades y aumenta la facilidad de hacer actualizaciones al sistema.


## Ventajas, limitaciones y casos de uso comunes.
Como ya habíamos mencionado anteriormente, algunas de las ventajas de la arquitectura basada en APIs pueden ser:
- La desacoplación de funcionalidades.
- Se puede reutilizar código.
- Es escalable.

### Limitaciones
- Si una api deja de funcionar todo lo relacionado también lo hará (Aunque es una ventaja que no deje de funcionar todo lo demás).
- Diseño minucioso del sistema a desarrollar.

## Ejemplo 
Un ejemplo de uso de CMS Headless puede ser el uso de APIs para obtener el contenido de una página web.
El sistema hace una solicitud para obtener ciertos datos de otro sistema, este los devuelve de forma plana para que 
el sistema que recibe los datos pueda darle el formato que este quiera.
Algo así no era posible anteriormente porque los datos estaban muy ligados en un único gran proyecto.

## Automatización y despliegue moderno.
### CI/CD

Por sus siglas en inglés, esto significa integración continua/entrega continua que se refiere a la
integración de código en una rama principal. Como vimos anteriormente se relaciona con trunk-based ya que si continuamente insertamos código agilizamos el proceso de desarrollo. La parte de entrega continua
hace referencia a la implementación del software lo más rápido posible en el mercado y varias veces en un mercado competitivo.
Hoy en día las actualizaciones son vitales en un sistema de software, por eso estas estrategias existen.

## Hosting estático vs dinámico.
Como su nombre lo dice los hosting estáticos y dinámicos se diferencian en que el estático es más tosco, el dinámico más interactivo.
No hay que denigrar al estatico, tiene sus ventajas, es más fácil de construir, económico, sus tiempos de carga son más rápidos, podemos decir que su fuerte son los sitios que no necesitan ser interactivos
y sólo necesitan mostrar información.
En cambio los sitios web dinámicos ofrecen una vista agradable, son fluidos, tienen animaciones e interacciones, si lo vemos detenidamente necesitan llamar la atención.
Hay diferencias claras entre ambos, sin embargo son igual de importantes y útiles.

## Flujo de despliegue automatizado.
Se refiere a la automatización del proceso de hacer commits, pull request, entre otras cosas para no hacer que los desarrolladores
pierdan el tiempo en tareas repetitivas. Esto agiliza entregas y puestas en producción.

# Fuentes
 - https://unirfp.unir.net/revista/ingenieria-y-tecnologia/framework/
 - https://codigofacilito.com/articulos/mvc-model-view-controller-explicado
 - https://digital55.com/blog/que-son-single-page-application-spa-desarrollo-elegido-por-gmail-linkedin/
 - https://es.wikipedia.org/wiki/Control_de_versiones
 - https://share.google/JCtEUCzC4K9IS0ZA6 
 - https://share.google/FpLyXrUgg0L2OdltP 
 - https://www.microsoft.com/es-es/security/business/security-101/what-is-authentication
 - https://www.fortinet.com/lat/resources/cyberglossary/authentication-token
 - https://www.vaadata.com/blog/jwt-json-web-token-vulnerabilities-common-attacks-and-security-best-practices/
 - https://auth0.com/es/intro-to-iam/what-is-oauth-2
 - https://www.jitterbit.com/es/blog/web-application-security-best-practices/
 - https://prismic.io/blog/headless-cms-vs-traditional-cms
 - https://geekflare.com/es/api-architecture-explained/
 - https://hygraph.com/blog/headless-cms-example
 - https://www.siteground.es/kb/sitio-web-estatico-vs-dinamico/
 - https://www.ilimit.com/es/blog/tecnologico-2/automatizacion-despliegue-continuo-30
 