django-pam
==========
A simple PAM authentication backend for Django.  Add the folder ``dpam``
somewhere on your python path and add 'dpam.backends.PAMBackend' to your
``settings.py``::

  AUTHENTICATION_BACKENDS = (
      ...
      'dpam.backends.PAMBackend',
      ...
  )

Now you can login via the system-login credentials.  If the user is
successfully authenticated but has never logged-in before, a new ``User``
object is created.  By default this new ``User`` has both ``is_staff`` and
``is_superuser`` set to ``False``.  You can change this behavior by adding
``PAM_IS_STAFF=True`` and ``PAM_IS_SUPERUSER`` in your ``settings.py`` file.
