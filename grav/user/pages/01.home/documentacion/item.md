---
title: Documentacion
content:
    items: '@self.children'
    limit: '5'
    order:
        by: date
        dir: desc
    pagination: '1'
    url_taxonomy_filters: '1'
show_sidebar: true
---

<html lang="en">
  <head>
        <!-- Google Tag Manager -->
        <script>(function(w,d,s,l,i){w[l]=w[l]||[];w[l].push({'gtm.start':
        new Date().getTime(),event:'gtm.js'});var f=d.getElementsByTagName(s)[0],
        j=d.createElement(s),dl=l!='dataLayer'?'&l='+l:'';j.async=true;j.src=
        'https://www.googletagmanager.com/gtm.js?id='+i+dl;f.parentNode.insertBefore(j,f);
        })(window,document,'script','dataLayer','GTM-TK2G9CM');</script>
        <!-- End Google Tag Manager -->
  </head>
  <body>
        <!-- Google Tag Manager (noscript) -->
        <noscript><iframe src="https://www.googletagmanager.com/ns.html?id=GTM-TK2G9CM"
          height="0" width="0" style="display:none;visibility:hidden"></iframe></noscript>
          <!-- End Google Tag Manager (noscript) -->

    <section>
    <div class="page-container float-right">
      		<div class="row">
           		 <div class="col-md-12">
              		<ul>
                    <h3><b>Estructura de la carpeta Grav CMS</b></h3>
                			<p ALIGN="justify">
                  				La carpeta de Grav contiene varios archivos, así que profundizaré un poco más en cada una de estas carpetas de nivel superior y explicaré para qué sirven:
                             </p>
                     
                             <ul>
                             	<li type="disc"><b>/assets</b></li>
                                     	<p>La carpeta assets es utilizada por el nuevo sistema de administración de activos dentro de Grav para almacenar archivos .css y .js procesados.</p>   
                             	<li type="disc"><b>/backup</b></li>
                                        <p>La carpeta backup es la ubicación predeterminada para las copias de seguridad Grav.</p>
	
								<li type="disc"><b>/bin</b></li>
                                    <p>La carpeta bin contiene la aplicación Grav CLI que se puede usar para realizar algunas tareas prácticas desde la línea de comandos.</p>

								<li type="disc"><b>/cache</b></li>                 
									<p>La carpeta de caché se usa para almacenar archivos temporales en caché que Grav genera automáticamente para mejorar el rendimiento.<br> 
										Esta carpeta no se debe utilizar para almacenar datos de usuarios, ya que se vacía de forma rutinaria de todos los datos.</p>        

								<li type="disc"><b>/images</b></li>
									<p>Grav viene con una biblioteca de manipulación de imágenes potente pero muy fácil de usar incorporada.<br> 
									   Estas imágenes se almacenan en la carpeta de imágenes para que puedan reutilizarse si se solicita nuevamente la misma imagen<br> 
									   con el mismo tamaño. Esta carpeta actúa como un caché de imágenes y está destinada a archivos generados automáticamente.</p>

								<li type="disc"><b>/logs</b></li>
									<p>Cuando Grav detecta un error, o si tiene activado el registro o la creación de perfiles adicionales,<br> 
										almacena los archivos de registro relevantes en la carpeta de registros.</p>

								<li type="disc"><b>/system</b></li>
									<p>La carpeta del sistema es donde los archivos que hacen que Grav realmente funcione.<br> 
										No debe editar nada en esta carpeta porque una actualización de Grav podría sobrescribir sus cambios.</p>

								<li type="disc"><b>/user</b></li>
									<p>Esta es la carpeta más importante para la mayoría de los usuarios de Grav.<br> 
									   Esta carpeta es donde pasará su tiempo creando contenido, utilizando complementos y editando sus temas.</p>

								<li type="disc"><b>/vendor</b></li> 
									<p>La carpeta del proveedor contiene bibliotecas importantes en las que se basa Grav.<br> 
									   Esta carpeta es similar a la carpeta /system en que su contenido no debe editarse a menos<br> 
									   que esté absolutamente seguro de lo que está haciendo.</p>
                                 <li type="disc"><b>/.Assets</b></li> 
									<p>Esta carpeta la usa el sistema de gestion de archivos para guardar los procesos, está carpeta tambien contiene un archivo .gitkeep 		 este archivo lo usa github para que no se bajen del repositorio carpetas vacias..</p>
                           	 </ul>
                           </ul>
                       </div>
                 </div>
  			</div>
    </section>
    
        <!-- loader -->
        <div id="ftco-loader" class="show fullscreen">
        <svg class="circular" width="48px" height="48px"><circle class="path-bg" cx="24" cy="24" r="22" fill="none" stroke-width="4" stroke="#eeeeee"/><circle class="path" cx="24" cy="24" r="22" fill="none" stroke-width="4" stroke-miterlimit="10" stroke="#F96D00"/></svg>
        </div>
  </body>
</html>