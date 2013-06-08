.. _models-title:

*********
El Modelo
*********

.. _class-Configuracion:

Clase Configuracion
===================
Encargada de las configuraciones generales de la aplicacion.

**Atributos**::

**periodoAcademicoActual:** Almacena el periodo academico en curso.
**periodoEvaluacionActual:** Almacena el periodo de evaluacion en curso.

**Descripción**::
Se hace uso de la clase Models que se encuentra en django.db.models para construir un nuevo modelo::

    from django.db import models

.. note::
    Para mas información consultar los Modelos_ en Django    

Se define la clase ``Configuracion`` con sus atributos::   

    class Configuracion(models.Model):
        periodoAcademicoActual = models.OneToOneField(
                        'PeriodoAcademico',
                         null=True, 
                         blank=True,
                         verbose_name='Periodo Académico Actual'
                         )
        periodoEvaluacionActual = models.OneToOneField(
                        'PeriodoEvaluacion', 
                        null=True, blank=True,
                         verbose_name='Periodo Evaluación Actual'
                         )
        @classmethod
        def getPeriodoAcademicoActual(self):
            return Configuracion.objects.get(id=1).periodoAcademicoActual

        @classmethod
        def getPeriodoEvaluacionActual(self):
            return Configuracion.objects.get(id=1).periodoEvaluacionActual
    
        class Meta:
            verbose_name = u'Configuraciones'
            verbose_name_plural = u'Configuraciones'

        def __unicode__(self):
            return u"Configuraciones de la Aplicación"


.. _class-OfertaAcademicaSGA:


Clase OfertaAcademicaSGA
========================

.. |enlace| replace:: esta frase reeplaza


.. _Python: http://www.python.org/


palabra Python_

palabra  |enlace|



.. note::
    Nota: una nota cualquiera

.. _class-PeriodoAcademico:

Clase PeriodoAcademico
======================

.. _class-Asignatura:

Clase Asignatura
================

.. _class-EstudiantePeriodoAcademico:

Clase EstudiantePeriodoAcademico
================================

.. _class-AsignaturaDocente:

Clase AsignaturaDocente
=======================

.. _class-DocentePeriodoAcademico:

Clase DocentePeriodoAcademico
=============================

.. _class-DireccionCarrera:

Clase DireccionCarrera
======================

.. _class-TipoInformante:

Clase TipoInformante
====================

.. _class-Cuestionario:

Clase Cuestionario
==================

.. _class-Contestacion:

Clase Contestacion
==================

.. _class-Evaluacion:

Clase Evaluacion
================

.. _class-Resultados:

Clase Resultados
================

.. _class-TipoPregunta:

Clase TipoPregunta
==================

.. _class-SeleccionUnica:

Clase SeleccionUnica
====================

.. _class-Ensayo:

Clase Ensayo
============

.. _class-Seccion:

Clase Seccion
=============

.. _class-Pregunta:

Clase Pregunta
==============

.. _class-ItemPregunta:

Clase ItemPregunta
==================

.. _class-AreaSGA:

Clase AreaSGA
=============

.. _class-PeriodoEvaluacion:

Clase PeriodoEvaluacion
=======================

.. _class-Tabulacion:

Class Tabulacion
================

.. _class-TabulacionEvaluacion2013:

Class TabulacionEvaluacion2013
==============================

.. _class-TabulacionAdicionales2012:

Class TabulacionAdicionales2012
===============================

.. _class-TabulacionSatisfaccion2012:

Class TabulacionSatisfaccion2012
================================

.. _class-Usuario:

Class Usuario
=============





.. _enlaces-modelos:

.. _Modelos: https://docs.djangoproject.com/en/dev/topics/db/models/






