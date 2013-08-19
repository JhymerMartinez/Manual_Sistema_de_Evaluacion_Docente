.. _templates-title:

**************
Las plantillas
**************

<<<<<<< HEAD
.. _template-intro:

Introducción
============

Una plantilla de Django es una cadena de texto pensada para separar la presentación de un documento de sus datos. Una plantilla define variables y varios trozos de lógica básica (tags) que regulan la manera en que debería mostrarse el documento. Normalmente, las plantillas se usan para producir HTML, pero las plantillas de Django son igualmente capaces de generar cualquier formato basado en texto.

Para el presente sistema se uso las plantillas que por defecto nos facilita Django, usadas en la parte de administración de cada proyecto. Por lo general, una vez intalado Python y Django, dichas plantillas se encuentran ubicadas en ``C:\Python27\Lib\site-packages\django-1.5.2-py2.7.egg\django\contrib\admin\templates\admin``.

Para mas información visitar: `curso de Django en español <http://www.maestrosdelweb.com/editorial/curso-django-las-plantillas/>`_.


.. _template-base:

Plantilla Base
==============
Contiene el diseño básico de las pantallas que se presentarán al usuario:

.. code-block:: html

	{% load admin_static %}<!DOCTYPE html>
	<html lang="{{ LANGUAGE_CODE|default:"en-us" }}" {% if LANGUAGE_BIDI %}dir="rtl"{% endif %}>
	<head>
	<title>{% block title %}{% endblock %}</title>
	<link rel="stylesheet" type="text/css" href="{% block stylesheet %}{% static "admin/css/base.css" %}{% endblock %}" />
	{% block extrastyle %}{% endblock %}
	<!--[if lte IE 7]><link rel="stylesheet" type="text/css" href="{% block stylesheet_ie %}{% static "admin/css/ie.css" %}{% endblock %}" /><![endif]-->
	{% if LANGUAGE_BIDI %}<link rel="stylesheet" type="text/css" href="{% block stylesheet_rtl %}{% static "admin/css/rtl.css" %}{% endblock %}" />{% endif %}
	<script type="text/javascript">window.__admin_media_prefix__ = "{% filter escapejs %}{% static "admin/" %}{% endfilter %}";</script>
	{% block extrahead %}{% endblock %}
	{% block blockbots %}<meta name="robots" content="NONE,NOARCHIVE" />{% endblock %}
	</head>
	{% load i18n %}

	<body class="{% if is_popup %}popup {% endif %}{% block bodyclass %}{% endblock %}">

	<!-- Container -->
	<div id="container">

	    {% if not is_popup %}
	    <!-- Header -->
	    <div id="header">
	        <div id="branding">
	        {% block branding %}{% endblock %}
	        </div>
	        {% if user.is_active and user.is_staff %}
	        <div id="user-tools">
	            {% trans 'Welcome,' %}
	            <strong>{% filter force_escape %}{% firstof user.get_short_name user.get_username %}{% endfilter %}</strong>.
	            {% block userlinks %}
	                {% url 'django-admindocs-docroot' as docsroot %}
	                {% if docsroot %}
	                    <a href="{{ docsroot }}">{% trans 'Documentation' %}</a> /
	                {% endif %}
	                {% if user.has_usable_password %}
	                <a href="{% url 'admin:password_change' %}">{% trans 'Change password' %}</a> /
	                {% endif %}
	                <a href="{% url 'admin:logout' %}">{% trans 'Log out' %}</a>
	            {% endblock %}
	        </div>
	        {% endif %}
	        {% block nav-global %}{% endblock %}
	    </div>
	    <!-- END Header -->
	    {% block breadcrumbs %}
	    <div class="breadcrumbs">
	    <a href="{% url 'admin:index' %}">{% trans 'Home' %}</a>
	    {% if title %} &rsaquo; {{ title }}{% endif %}
	    </div>
	    {% endblock %}
	    {% endif %}

	    {% block messages %}
	        {% if messages %}
	        <ul class="messagelist">{% for message in messages %}
	          <li{% if message.tags %} class="{{ message.tags }}"{% endif %}>{{ message }}</li>
	        {% endfor %}</ul>
	        {% endif %}
	    {% endblock messages %}

	    <!-- Content -->
	    <div id="content" class="{% block coltype %}colM{% endblock %}">
	        {% block pretitle %}{% endblock %}
	        {% block content_title %}{% if title %}<h1>{{ title }}</h1>{% endif %}{% endblock %}
	        {% block content %}
	        {% block object-tools %}{% endblock %}
	        {{ content }}
	        {% endblock %}
	        {% block sidebar %}{% endblock %}
	        <br class="clear" />
	    </div>
	    <!-- END Content -->

	    {% block footer %}<div id="footer"></div>{% endblock %}
	</div>
	<!-- END Container -->

	</body>
	</html>

		

.. _template-admin:

Plantillas para Administración
==============================

.. _template-admin-signatures:

Asignaturas y docentes
----------------------

.. _template-admin-evaluation:

Evaluaciones
------------

.. _template-admin-period:

Período académico
-----------------

.. _template-admin-question:

Preguntas en general
--------------------




.. _template-user:

Plantillas para usuarios y tareas
=================================
=======

>>>>>>> a1262be8a806de79578080345dc566d4e4eb5093





