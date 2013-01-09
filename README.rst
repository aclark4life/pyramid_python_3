Heroku Python 3.3 Bug
=====================

This repository demonstrates a bug with the Heroku Python 3.3 environment, see:

- https://github.com/Pylons/pyramid/issues/785

for more information.

::

    aclark@Alexs-MacBook-Pro:~/Developer/pyramid_python_3/ > git push heroku master
    Counting objects: 6, done.
    Delta compression using up to 2 threads.
    Compressing objects: 100% (3/3), done.
    Writing objects: 100% (6/6), 655 bytes, done.
    Total 6 (delta 0), reused 0 (delta 0)
    -----> Python app detected
    -----> Preparing Python runtime (python-3.3.0)
    -----> Installing Distribute (0.6.34)
    -----> Installing Pip (1.2.1)
    -----> Installing dependencies using Pip (1.2.1)
           Downloading/unpacking pyramid (from -r requirements.txt (line 1))
             Running setup.py egg_info for package pyramid
               
           Downloading/unpacking Chameleon>=1.2.3 (from pyramid->-r requirements.txt (line 1))
             Running setup.py egg_info for package Chameleon
               
           Downloading/unpacking Mako>=0.3.6 (from pyramid->-r requirements.txt (line 1))
             Running setup.py egg_info for package Mako
               
               warning: no files found matching '*.xml' under directory 'examples'
               warning: no files found matching '*.mako' under directory 'examples'
               warning: no files found matching 'ez_setup.py'
               no previously-included directories found matching 'doc/build/output'
           Downloading/unpacking WebOb>=1.2b3 (from pyramid->-r requirements.txt (line 1))
             Running setup.py egg_info for package WebOb
               
               no previously-included directories found matching '*.pyc'
               no previously-included directories found matching '*.pyo'
           Downloading/unpacking repoze.lru>=0.4 (from pyramid->-r requirements.txt (line 1))
             Downloading repoze.lru-0.6.tar.gz
             Running setup.py egg_info for package repoze.lru
               
           Downloading/unpacking zope.interface>=3.8.0 (from pyramid->-r requirements.txt (line 1))
             Running setup.py egg_info for package zope.interface
               
           Downloading/unpacking zope.deprecation>=3.5.0 (from pyramid->-r requirements.txt (line 1))
             Downloading zope.deprecation-4.0.2.tar.gz
             Running setup.py egg_info for package zope.deprecation
               
           Downloading/unpacking venusian>=1.0a3 (from pyramid->-r requirements.txt (line 1))
             Running setup.py egg_info for package venusian
               
           Downloading/unpacking translationstring>=0.4 (from pyramid->-r requirements.txt (line 1))
             Downloading translationstring-1.1.tar.gz
             Running setup.py egg_info for package translationstring
               
               no previously-included directories found matching 'docs/_build'
           Downloading/unpacking PasteDeploy>=1.5.0 (from pyramid->-r requirements.txt (line 1))
             Downloading PasteDeploy-1.5.0.tar.gz
             Running setup.py egg_info for package PasteDeploy
               
           Downloading/unpacking MarkupSafe>=0.9.2 (from Mako>=0.3.6->pyramid->-r requirements.txt (line 1))
             Downloading MarkupSafe-0.15.tar.gz
             Running setup.py egg_info for package MarkupSafe
               
           Installing collected packages: pyramid, Chameleon, Mako, WebOb, repoze.lru, zope.interface, zope.deprecation, venusian, translationstring, PasteDeploy, MarkupSafe
             Running setup.py install for pyramid
               
               Traceback (most recent call last):
                 File "<string>", line 1, in <module>
                 File "/app/build/pyramid/setup.py", line 122, in <module>
                   """
                 File "/app/.heroku/python/lib/python3.3/distutils/core.py", line 148, in setup
                   dist.run_commands()
                 File "/app/.heroku/python/lib/python3.3/distutils/dist.py", line 917, in run_commands
                   self.run_command(cmd)
                 File "/app/.heroku/python/lib/python3.3/distutils/dist.py", line 936, in run_command
                   cmd_obj.run()
                 File "/app/.heroku/python/lib/python3.3/site-packages/distribute-0.6.34-py3.3.egg/setuptools/command/install.py", line 53, in run
                   return _install.run(self)
                 File "/app/.heroku/python/lib/python3.3/distutils/command/install.py", line 569, in run
                   self.run_command('build')
                 File "/app/.heroku/python/lib/python3.3/distutils/cmd.py", line 313, in run_command
                   self.distribution.run_command(command)
                 File "/app/.heroku/python/lib/python3.3/distutils/dist.py", line 936, in run_command
                   cmd_obj.run()
                 File "/app/.heroku/python/lib/python3.3/distutils/command/build.py", line 126, in run
                   self.run_command(cmd_name)
                 File "/app/.heroku/python/lib/python3.3/distutils/cmd.py", line 313, in run_command
                   self.distribution.run_command(command)
                 File "/app/.heroku/python/lib/python3.3/distutils/dist.py", line 936, in run_command
                   cmd_obj.run()
                 File "/app/.heroku/python/lib/python3.3/site-packages/distribute-0.6.34-py3.3.egg/setuptools/command/build_py.py", line 90, in run
                   self.build_package_data()
                 File "/app/.heroku/python/lib/python3.3/site-packages/distribute-0.6.34-py3.3.egg/setuptools/command/build_py.py", line 150, in build_package_data
                   outf, copied = self.copy_file(srcfile, target)
                 File "/app/.heroku/python/lib/python3.3/distutils/cmd.py", line 348, in copy_file
                   dry_run=self.dry_run)
                 File "/app/.heroku/python/lib/python3.3/distutils/file_util.py", line 102, in copy_file
                   if not os.path.isfile(src):
                 File "/app/.heroku/python/lib/python3.3/genericpath.py", line 29, in isfile
                   st = os.stat(path)
               UnicodeEncodeError: 'ascii' codec can't encode character '\xe9' in position 31: ordinal not in range(128)
               Complete output from command /app/.heroku/python/bin/python -c "import setuptools;__file__='/app/build/pyramid/setup.py';exec(compile(open(__file__).read().replace('\r\n', '\n'), __file__, 'exec'))" install --single-version-externally-managed --record /tmp/pip-a7sbnh-record/install-record.txt:
               running install
           
           running build
           
           running build_py
           
           creating build
           
           creating build/lib
           
           creating build/lib/pyramid
           
           copying pyramid/compat.py -> build/lib/pyramid
           
           copying pyramid/authorization.py -> build/lib/pyramid
           
           copying pyramid/security.py -> build/lib/pyramid
           
           copying pyramid/request.py -> build/lib/pyramid
           
           copying pyramid/view.py -> build/lib/pyramid
           
           copying pyramid/exceptions.py -> build/lib/pyramid
           
           copying pyramid/response.py -> build/lib/pyramid
           
           copying pyramid/interfaces.py -> build/lib/pyramid
           
           copying pyramid/threadlocal.py -> build/lib/pyramid
           
           copying pyramid/events.py -> build/lib/pyramid
           
           copying pyramid/util.py -> build/lib/pyramid
           
           copying pyramid/session.py -> build/lib/pyramid
           
           copying pyramid/urldispatch.py -> build/lib/pyramid
           
           copying pyramid/url.py -> build/lib/pyramid
           
           copying pyramid/encode.py -> build/lib/pyramid
           
           copying pyramid/settings.py -> build/lib/pyramid
           
           copying pyramid/i18n.py -> build/lib/pyramid
           
           copying pyramid/chameleon_text.py -> build/lib/pyramid
           
           copying pyramid/scripting.py -> build/lib/pyramid
           
           copying pyramid/authentication.py -> build/lib/pyramid
           
           copying pyramid/httpexceptions.py -> build/lib/pyramid
           
           copying pyramid/registry.py -> build/lib/pyramid
           
           copying pyramid/renderers.py -> build/lib/pyramid
           
           copying pyramid/wsgi.py -> build/lib/pyramid
           
           copying pyramid/static.py -> build/lib/pyramid
           
           copying pyramid/location.py -> build/lib/pyramid
           
           copying pyramid/tweens.py -> build/lib/pyramid
           
           copying pyramid/asset.py -> build/lib/pyramid
           
           copying pyramid/resource.py -> build/lib/pyramid
           
           copying pyramid/__init__.py -> build/lib/pyramid
           
           copying pyramid/testing.py -> build/lib/pyramid
           
           copying pyramid/decorator.py -> build/lib/pyramid
           
           copying pyramid/traversal.py -> build/lib/pyramid
           
           copying pyramid/paster.py -> build/lib/pyramid
           
           copying pyramid/mako_templating.py -> build/lib/pyramid
           
           copying pyramid/path.py -> build/lib/pyramid
           
           copying pyramid/chameleon_zpt.py -> build/lib/pyramid
           
           copying pyramid/router.py -> build/lib/pyramid
           
           creating build/lib/pyramid/scaffolds
           
           copying pyramid/scaffolds/copydir.py -> build/lib/pyramid/scaffolds
           
           copying pyramid/scaffolds/template.py -> build/lib/pyramid/scaffolds
           
           copying pyramid/scaffolds/__init__.py -> build/lib/pyramid/scaffolds
           
           copying pyramid/scaffolds/tests.py -> build/lib/pyramid/scaffolds
           
           creating build/lib/pyramid/tests
           
           copying pyramid/tests/test_session.py -> build/lib/pyramid/tests
           
           copying pyramid/tests/test_wsgi.py -> build/lib/pyramid/tests
           
           copying pyramid/tests/test_traversal.py -> build/lib/pyramid/tests
           
           copying pyramid/tests/test_encode.py -> build/lib/pyramid/tests
           
           copying pyramid/tests/test_router.py -> build/lib/pyramid/tests
           
           copying pyramid/tests/test_static.py -> build/lib/pyramid/tests
           
           copying pyramid/tests/test_chameleon_zpt.py -> build/lib/pyramid/tests
           
           copying pyramid/tests/test_settings.py -> build/lib/pyramid/tests
           
           copying pyramid/tests/test_asset.py -> build/lib/pyramid/tests
           
           copying pyramid/tests/test_location.py -> build/lib/pyramid/tests
           
           copying pyramid/tests/test_security.py -> build/lib/pyramid/tests
           
           copying pyramid/tests/test_url.py -> build/lib/pyramid/tests
           
           copying pyramid/tests/test_urldispatch.py -> build/lib/pyramid/tests
           
           copying pyramid/tests/test_docs.py -> build/lib/pyramid/tests
           
           copying pyramid/tests/test_mako_templating.py -> build/lib/pyramid/tests
           
           copying pyramid/tests/test_path.py -> build/lib/pyramid/tests
           
           copying pyramid/tests/test_chameleon_text.py -> build/lib/pyramid/tests
           
           copying pyramid/tests/test_renderers.py -> build/lib/pyramid/tests
           
           copying pyramid/tests/test_authorization.py -> build/lib/pyramid/tests
           
           copying pyramid/tests/test_authentication.py -> build/lib/pyramid/tests
           
           copying pyramid/tests/test_registry.py -> build/lib/pyramid/tests
           
           copying pyramid/tests/test_decorator.py -> build/lib/pyramid/tests
           
           copying pyramid/tests/test_view.py -> build/lib/pyramid/tests
           
           copying pyramid/tests/test_threadlocal.py -> build/lib/pyramid/tests
           
           copying pyramid/tests/test_request.py -> build/lib/pyramid/tests
           
           copying pyramid/tests/test_scripting.py -> build/lib/pyramid/tests
           
           copying pyramid/tests/test_exceptions.py -> build/lib/pyramid/tests
           
           copying pyramid/tests/test_response.py -> build/lib/pyramid/tests
           
           copying pyramid/tests/test_testing.py -> build/lib/pyramid/tests
           
           copying pyramid/tests/__init__.py -> build/lib/pyramid/tests
           
           copying pyramid/tests/test_httpexceptions.py -> build/lib/pyramid/tests
           
           copying pyramid/tests/test_events.py -> build/lib/pyramid/tests
           
           copying pyramid/tests/test_integration.py -> build/lib/pyramid/tests
           
           copying pyramid/tests/test_util.py -> build/lib/pyramid/tests
           
           copying pyramid/tests/test_paster.py -> build/lib/pyramid/tests
           
           copying pyramid/tests/test_i18n.py -> build/lib/pyramid/tests
           
           creating build/lib/pyramid/fixers
           
           copying pyramid/fixers/fix_bfg_imports.py -> build/lib/pyramid/fixers
           
           copying pyramid/fixers/__init__.py -> build/lib/pyramid/fixers
           
           creating build/lib/pyramid/scripts
           
           copying pyramid/scripts/pserve.py -> build/lib/pyramid/scripts
           
           copying pyramid/scripts/proutes.py -> build/lib/pyramid/scripts
           
           copying pyramid/scripts/pviews.py -> build/lib/pyramid/scripts
           
           copying pyramid/scripts/pcreate.py -> build/lib/pyramid/scripts
           
           copying pyramid/scripts/common.py -> build/lib/pyramid/scripts
           
           copying pyramid/scripts/prequest.py -> build/lib/pyramid/scripts
           
           copying pyramid/scripts/pshell.py -> build/lib/pyramid/scripts
           
           copying pyramid/scripts/__init__.py -> build/lib/pyramid/scripts
           
           copying pyramid/scripts/ptweens.py -> build/lib/pyramid/scripts
           
           creating build/lib/pyramid/config
           
           copying pyramid/config/predicates.py -> build/lib/pyramid/config
           
           copying pyramid/config/security.py -> build/lib/pyramid/config
           
           copying pyramid/config/views.py -> build/lib/pyramid/config
           
           copying pyramid/config/assets.py -> build/lib/pyramid/config
           
           copying pyramid/config/util.py -> build/lib/pyramid/config
           
           copying pyramid/config/rendering.py -> build/lib/pyramid/config
           
           copying pyramid/config/settings.py -> build/lib/pyramid/config
           
           copying pyramid/config/i18n.py -> build/lib/pyramid/config
           
           copying pyramid/config/tweens.py -> build/lib/pyramid/config
           
           copying pyramid/config/factories.py -> build/lib/pyramid/config
           
           copying pyramid/config/__init__.py -> build/lib/pyramid/config
           
           copying pyramid/config/adapters.py -> build/lib/pyramid/config
           
           copying pyramid/config/testing.py -> build/lib/pyramid/config
           
           copying pyramid/config/routes.py -> build/lib/pyramid/config
           
           copying pyramid/config/zca.py -> build/lib/pyramid/config
           
           creating build/lib/pyramid/tests/pkgs
           
           copying pyramid/tests/pkgs/__init__.py -> build/lib/pyramid/tests/pkgs
           
           creating build/lib/pyramid/tests/test_scripts
           
           copying pyramid/tests/test_scripts/test_proutes.py -> build/lib/pyramid/tests/test_scripts
           
           copying pyramid/tests/test_scripts/test_prequest.py -> build/lib/pyramid/tests/test_scripts
           
           copying pyramid/tests/test_scripts/test_pcreate.py -> build/lib/pyramid/tests/test_scripts
           
           copying pyramid/tests/test_scripts/test_pviews.py -> build/lib/pyramid/tests/test_scripts
           
           copying pyramid/tests/test_scripts/dummy.py -> build/lib/pyramid/tests/test_scripts
           
           copying pyramid/tests/test_scripts/test_common.py -> build/lib/pyramid/tests/test_scripts
           
           copying pyramid/tests/test_scripts/test_ptweens.py -> build/lib/pyramid/tests/test_scripts
           
           copying pyramid/tests/test_scripts/test_pserve.py -> build/lib/pyramid/tests/test_scripts
           
           copying pyramid/tests/test_scripts/test_pshell.py -> build/lib/pyramid/tests/test_scripts
           
           copying pyramid/tests/test_scripts/__init__.py -> build/lib/pyramid/tests/test_scripts
           
           creating build/lib/pyramid/tests/test_config
           
           copying pyramid/tests/test_config/test_rendering.py -> build/lib/pyramid/tests/test_config
           
           copying pyramid/tests/test_config/test_adapters.py -> build/lib/pyramid/tests/test_config
           
           copying pyramid/tests/test_config/test_settings.py -> build/lib/pyramid/tests/test_config
           
           copying pyramid/tests/test_config/test_security.py -> build/lib/pyramid/tests/test_config
           
           copying pyramid/tests/test_config/test_routes.py -> build/lib/pyramid/tests/test_config
           
           copying pyramid/tests/test_config/test_predicates.py -> build/lib/pyramid/tests/test_config
           
           copying pyramid/tests/test_config/test_assets.py -> build/lib/pyramid/tests/test_config
           
           copying pyramid/tests/test_config/test_testing.py -> build/lib/pyramid/tests/test_config
           
           copying pyramid/tests/test_config/__init__.py -> build/lib/pyramid/tests/test_config
           
           copying pyramid/tests/test_config/test_factories.py -> build/lib/pyramid/tests/test_config
           
           copying pyramid/tests/test_config/test_util.py -> build/lib/pyramid/tests/test_config
           
           copying pyramid/tests/test_config/test_i18n.py -> build/lib/pyramid/tests/test_config
           
           copying pyramid/tests/test_config/test_views.py -> build/lib/pyramid/tests/test_config
           
           copying pyramid/tests/test_config/test_tweens.py -> build/lib/pyramid/tests/test_config
           
           copying pyramid/tests/test_config/test_init.py -> build/lib/pyramid/tests/test_config
           
           creating build/lib/pyramid/tests/test_scaffolds
           
           copying pyramid/tests/test_scaffolds/test_template.py -> build/lib/pyramid/tests/test_scaffolds
           
           copying pyramid/tests/test_scaffolds/__init__.py -> build/lib/pyramid/tests/test_scaffolds
           
           copying pyramid/tests/test_scaffolds/test_copydir.py -> build/lib/pyramid/tests/test_scaffolds
           
           copying pyramid/tests/test_scaffolds/test_init.py -> build/lib/pyramid/tests/test_scaffolds
           
           creating build/lib/pyramid/tests/pkgs/notfoundview
           
           copying pyramid/tests/pkgs/notfoundview/__init__.py -> build/lib/pyramid/tests/pkgs/notfoundview
           
           creating build/lib/pyramid/tests/pkgs/forbiddenview
           
           copying pyramid/tests/pkgs/forbiddenview/__init__.py -> build/lib/pyramid/tests/pkgs/forbiddenview
           
           creating build/lib/pyramid/tests/pkgs/includeapp1
           
           copying pyramid/tests/pkgs/includeapp1/root.py -> build/lib/pyramid/tests/pkgs/includeapp1
           
           copying pyramid/tests/pkgs/includeapp1/two.py -> build/lib/pyramid/tests/pkgs/includeapp1
           
           copying pyramid/tests/pkgs/includeapp1/three.py -> build/lib/pyramid/tests/pkgs/includeapp1
           
           copying pyramid/tests/pkgs/includeapp1/__init__.py -> build/lib/pyramid/tests/pkgs/includeapp1
           
           creating build/lib/pyramid/tests/pkgs/forbiddenapp
           
           copying pyramid/tests/pkgs/forbiddenapp/__init__.py -> build/lib/pyramid/tests/pkgs/forbiddenapp
           
           creating build/lib/pyramid/tests/pkgs/rendererscanapp
           
           copying pyramid/tests/pkgs/rendererscanapp/__init__.py -> build/lib/pyramid/tests/pkgs/rendererscanapp
           
           creating build/lib/pyramid/tests/pkgs/conflictapp
           
           copying pyramid/tests/pkgs/conflictapp/included.py -> build/lib/pyramid/tests/pkgs/conflictapp
           
           copying pyramid/tests/pkgs/conflictapp/__init__.py -> build/lib/pyramid/tests/pkgs/conflictapp
           
           creating build/lib/pyramid/tests/pkgs/fixtureapp
           
           copying pyramid/tests/pkgs/fixtureapp/views.py -> build/lib/pyramid/tests/pkgs/fixtureapp
           
           copying pyramid/tests/pkgs/fixtureapp/__init__.py -> build/lib/pyramid/tests/pkgs/fixtureapp
           
           copying pyramid/tests/pkgs/fixtureapp/models.py -> build/lib/pyramid/tests/pkgs/fixtureapp
           
           creating build/lib/pyramid/tests/pkgs/static_assetspec
           
           copying pyramid/tests/pkgs/static_assetspec/__init__.py -> build/lib/pyramid/tests/pkgs/static_assetspec
           
           creating build/lib/pyramid/tests/pkgs/subrequestapp
           
           copying pyramid/tests/pkgs/subrequestapp/__init__.py -> build/lib/pyramid/tests/pkgs/subrequestapp
           
           creating build/lib/pyramid/tests/pkgs/defpermbugapp
           
           copying pyramid/tests/pkgs/defpermbugapp/__init__.py -> build/lib/pyramid/tests/pkgs/defpermbugapp
           
           creating build/lib/pyramid/tests/pkgs/localeapp
           
           copying pyramid/tests/pkgs/localeapp/__init__.py -> build/lib/pyramid/tests/pkgs/localeapp
           
           creating build/lib/pyramid/tests/pkgs/static_routeprefix
           
           copying pyramid/tests/pkgs/static_routeprefix/__init__.py -> build/lib/pyramid/tests/pkgs/static_routeprefix
           
           creating build/lib/pyramid/tests/pkgs/ccbugapp
           
           copying pyramid/tests/pkgs/ccbugapp/__init__.py -> build/lib/pyramid/tests/pkgs/ccbugapp
           
           creating build/lib/pyramid/tests/pkgs/permbugapp
           
           copying pyramid/tests/pkgs/permbugapp/__init__.py -> build/lib/pyramid/tests/pkgs/permbugapp
           
           creating build/lib/pyramid/tests/pkgs/wsgiapp2app
           
           copying pyramid/tests/pkgs/wsgiapp2app/__init__.py -> build/lib/pyramid/tests/pkgs/wsgiapp2app
           
           creating build/lib/pyramid/tests/pkgs/eventonly
           
           copying pyramid/tests/pkgs/eventonly/__init__.py -> build/lib/pyramid/tests/pkgs/eventonly
           
           creating build/lib/pyramid/tests/pkgs/hybridapp
           
           copying pyramid/tests/pkgs/hybridapp/views.py -> build/lib/pyramid/tests/pkgs/hybridapp
           
           copying pyramid/tests/pkgs/hybridapp/__init__.py -> build/lib/pyramid/tests/pkgs/hybridapp
           
           creating build/lib/pyramid/tests/pkgs/exceptionviewapp
           
           copying pyramid/tests/pkgs/exceptionviewapp/views.py -> build/lib/pyramid/tests/pkgs/exceptionviewapp
           
           copying pyramid/tests/pkgs/exceptionviewapp/__init__.py -> build/lib/pyramid/tests/pkgs/exceptionviewapp
           
           copying pyramid/tests/pkgs/exceptionviewapp/models.py -> build/lib/pyramid/tests/pkgs/exceptionviewapp
           
           creating build/lib/pyramid/tests/pkgs/static_abspath
           
           copying pyramid/tests/pkgs/static_abspath/__init__.py -> build/lib/pyramid/tests/pkgs/static_abspath
           
           creating build/lib/pyramid/tests/pkgs/staticpermapp
           
           copying pyramid/tests/pkgs/staticpermapp/__init__.py -> build/lib/pyramid/tests/pkgs/staticpermapp
           
           creating build/lib/pyramid/tests/pkgs/viewdecoratorapp
           
           copying pyramid/tests/pkgs/viewdecoratorapp/__init__.py -> build/lib/pyramid/tests/pkgs/viewdecoratorapp
           
           creating build/lib/pyramid/tests/pkgs/restbugapp
           
           copying pyramid/tests/pkgs/restbugapp/views.py -> build/lib/pyramid/tests/pkgs/restbugapp
           
           copying pyramid/tests/pkgs/restbugapp/__init__.py -> build/lib/pyramid/tests/pkgs/restbugapp
           
           creating build/lib/pyramid/tests/test_config/pkgs
           
           copying pyramid/tests/test_config/pkgs/__init__.py -> build/lib/pyramid/tests/test_config/pkgs
           
           creating build/lib/pyramid/tests/pkgs/rendererscanapp/two
           
           copying pyramid/tests/pkgs/rendererscanapp/two/__init__.py -> build/lib/pyramid/tests/pkgs/rendererscanapp/two
           
           creating build/lib/pyramid/tests/pkgs/fixtureapp/subpackage
           
           copying pyramid/tests/pkgs/fixtureapp/subpackage/__init__.py -> build/lib/pyramid/tests/pkgs/fixtureapp/subpackage
           
           creating build/lib/pyramid/tests/pkgs/viewdecoratorapp/views
           
           copying pyramid/tests/pkgs/viewdecoratorapp/views/views.py -> build/lib/pyramid/tests/pkgs/viewdecoratorapp/views
           
           copying pyramid/tests/pkgs/viewdecoratorapp/views/__init__.py -> build/lib/pyramid/tests/pkgs/viewdecoratorapp/views
           
           creating build/lib/pyramid/tests/test_config/pkgs/scanextrakw
           
           copying pyramid/tests/test_config/pkgs/scanextrakw/__init__.py -> build/lib/pyramid/tests/test_config/pkgs/scanextrakw
           
           creating build/lib/pyramid/tests/test_config/pkgs/scannable
           
           copying pyramid/tests/test_config/pkgs/scannable/another.py -> build/lib/pyramid/tests/test_config/pkgs/scannable
           
           copying pyramid/tests/test_config/pkgs/scannable/__init__.py -> build/lib/pyramid/tests/test_config/pkgs/scannable
           
           creating build/lib/pyramid/tests/test_config/pkgs/asset
           
           copying pyramid/tests/test_config/pkgs/asset/views.py -> build/lib/pyramid/tests/test_config/pkgs/asset
           
           copying pyramid/tests/test_config/pkgs/asset/__init__.py -> build/lib/pyramid/tests/test_config/pkgs/asset
           
           copying pyramid/tests/test_config/pkgs/asset/models.py -> build/lib/pyramid/tests/test_config/pkgs/asset
           
           creating build/lib/pyramid/tests/test_config/pkgs/selfscan
           
           copying pyramid/tests/test_config/pkgs/selfscan/another.py -> build/lib/pyramid/tests/test_config/pkgs/selfscan
           
           copying pyramid/tests/test_config/pkgs/selfscan/__init__.py -> build/lib/pyramid/tests/test_config/pkgs/selfscan
           
           creating build/lib/pyramid/tests/test_config/pkgs/scannable/subpackage
           
           copying pyramid/tests/test_config/pkgs/scannable/subpackage/notinit.py -> build/lib/pyramid/tests/test_config/pkgs/scannable/subpackage
           
           copying pyramid/tests/test_config/pkgs/scannable/subpackage/__init__.py -> build/lib/pyramid/tests/test_config/pkgs/scannable/subpackage
           
           creating build/lib/pyramid/tests/test_config/pkgs/asset/subpackage
           
           copying pyramid/tests/test_config/pkgs/asset/subpackage/__init__.py -> build/lib/pyramid/tests/test_config/pkgs/asset/subpackage
           
           creating build/lib/pyramid/tests/test_config/pkgs/scannable/subpackage/subsubpackage
           
           copying pyramid/tests/test_config/pkgs/scannable/subpackage/subsubpackage/__init__.py -> build/lib/pyramid/tests/test_config/pkgs/scannable/subpackage/subsubpackage
           
           running egg_info
           
           writing pyramid.egg-info/PKG-INFO
           
           writing top-level names to pyramid.egg-info/top_level.txt
           
           writing dependency_links to pyramid.egg-info/dependency_links.txt
           
           writing entry points to pyramid.egg-info/entry_points.txt
           
           writing requirements to pyramid.egg-info/requires.txt
           
           warning: manifest_maker: standard file '-c' not found
           
           
           
           reading manifest file 'pyramid.egg-info/SOURCES.txt'
           
           writing manifest file 'pyramid.egg-info/SOURCES.txt'
           
           creating build/lib/pyramid/scaffolds/alchemy
           
           copying pyramid/scaffolds/alchemy/CHANGES.txt_tmpl -> build/lib/pyramid/scaffolds/alchemy
           
           copying pyramid/scaffolds/alchemy/MANIFEST.in_tmpl -> build/lib/pyramid/scaffolds/alchemy
           
           copying pyramid/scaffolds/alchemy/README.txt_tmpl -> build/lib/pyramid/scaffolds/alchemy
           
           copying pyramid/scaffolds/alchemy/development.ini_tmpl -> build/lib/pyramid/scaffolds/alchemy
           
           copying pyramid/scaffolds/alchemy/production.ini_tmpl -> build/lib/pyramid/scaffolds/alchemy
           
           copying pyramid/scaffolds/alchemy/setup.cfg_tmpl -> build/lib/pyramid/scaffolds/alchemy
           
           copying pyramid/scaffolds/alchemy/setup.py_tmpl -> build/lib/pyramid/scaffolds/alchemy
           
           creating build/lib/pyramid/scaffolds/alchemy/+package+
           
           copying pyramid/scaffolds/alchemy/+package+/__init__.py -> build/lib/pyramid/scaffolds/alchemy/+package+
           
           copying pyramid/scaffolds/alchemy/+package+/models.py -> build/lib/pyramid/scaffolds/alchemy/+package+
           
           copying pyramid/scaffolds/alchemy/+package+/tests.py_tmpl -> build/lib/pyramid/scaffolds/alchemy/+package+
           
           copying pyramid/scaffolds/alchemy/+package+/views.py_tmpl -> build/lib/pyramid/scaffolds/alchemy/+package+
           
           creating build/lib/pyramid/scaffolds/alchemy/+package+/scripts
           
           copying pyramid/scaffolds/alchemy/+package+/scripts/__init__.py -> build/lib/pyramid/scaffolds/alchemy/+package+/scripts
           
           copying pyramid/scaffolds/alchemy/+package+/scripts/initializedb.py -> build/lib/pyramid/scaffolds/alchemy/+package+/scripts
           
           creating build/lib/pyramid/scaffolds/alchemy/+package+/static
           
           copying pyramid/scaffolds/alchemy/+package+/static/favicon.ico -> build/lib/pyramid/scaffolds/alchemy/+package+/static
           
           copying pyramid/scaffolds/alchemy/+package+/static/footerbg.png -> build/lib/pyramid/scaffolds/alchemy/+package+/static
           
           copying pyramid/scaffolds/alchemy/+package+/static/headerbg.png -> build/lib/pyramid/scaffolds/alchemy/+package+/static
           
           copying pyramid/scaffolds/alchemy/+package+/static/ie6.css -> build/lib/pyramid/scaffolds/alchemy/+package+/static
           
           copying pyramid/scaffolds/alchemy/+package+/static/middlebg.png -> build/lib/pyramid/scaffolds/alchemy/+package+/static
           
           copying pyramid/scaffolds/alchemy/+package+/static/pylons.css -> build/lib/pyramid/scaffolds/alchemy/+package+/static
           
           copying pyramid/scaffolds/alchemy/+package+/static/pyramid-small.png -> build/lib/pyramid/scaffolds/alchemy/+package+/static
           
           copying pyramid/scaffolds/alchemy/+package+/static/pyramid.png -> build/lib/pyramid/scaffolds/alchemy/+package+/static
           
           copying pyramid/scaffolds/alchemy/+package+/static/transparent.gif -> build/lib/pyramid/scaffolds/alchemy/+package+/static
           
           creating build/lib/pyramid/scaffolds/alchemy/+package+/templates
           
           copying pyramid/scaffolds/alchemy/+package+/templates/mytemplate.pt_tmpl -> build/lib/pyramid/scaffolds/alchemy/+package+/templates
           
           creating build/lib/pyramid/scaffolds/starter
           
           copying pyramid/scaffolds/starter/CHANGES.txt_tmpl -> build/lib/pyramid/scaffolds/starter
           
           copying pyramid/scaffolds/starter/MANIFEST.in_tmpl -> build/lib/pyramid/scaffolds/starter
           
           copying pyramid/scaffolds/starter/README.txt_tmpl -> build/lib/pyramid/scaffolds/starter
           
           copying pyramid/scaffolds/starter/development.ini_tmpl -> build/lib/pyramid/scaffolds/starter
           
           copying pyramid/scaffolds/starter/production.ini_tmpl -> build/lib/pyramid/scaffolds/starter
           
           copying pyramid/scaffolds/starter/setup.cfg_tmpl -> build/lib/pyramid/scaffolds/starter
           
           copying pyramid/scaffolds/starter/setup.py_tmpl -> build/lib/pyramid/scaffolds/starter
           
           creating build/lib/pyramid/scaffolds/starter/+package+
           
           copying pyramid/scaffolds/starter/+package+/__init__.py -> build/lib/pyramid/scaffolds/starter/+package+
           
           copying pyramid/scaffolds/starter/+package+/tests.py_tmpl -> build/lib/pyramid/scaffolds/starter/+package+
           
           copying pyramid/scaffolds/starter/+package+/views.py_tmpl -> build/lib/pyramid/scaffolds/starter/+package+
           
           creating build/lib/pyramid/scaffolds/starter/+package+/static
           
           copying pyramid/scaffolds/starter/+package+/static/favicon.ico -> build/lib/pyramid/scaffolds/starter/+package+/static
           
           copying pyramid/scaffolds/starter/+package+/static/footerbg.png -> build/lib/pyramid/scaffolds/starter/+package+/static
           
           copying pyramid/scaffolds/starter/+package+/static/headerbg.png -> build/lib/pyramid/scaffolds/starter/+package+/static
           
           copying pyramid/scaffolds/starter/+package+/static/ie6.css -> build/lib/pyramid/scaffolds/starter/+package+/static
           
           copying pyramid/scaffolds/starter/+package+/static/middlebg.png -> build/lib/pyramid/scaffolds/starter/+package+/static
           
           copying pyramid/scaffolds/starter/+package+/static/pylons.css -> build/lib/pyramid/scaffolds/starter/+package+/static
           
           copying pyramid/scaffolds/starter/+package+/static/pyramid-small.png -> build/lib/pyramid/scaffolds/starter/+package+/static
           
           copying pyramid/scaffolds/starter/+package+/static/pyramid.png -> build/lib/pyramid/scaffolds/starter/+package+/static
           
           copying pyramid/scaffolds/starter/+package+/static/transparent.gif -> build/lib/pyramid/scaffolds/starter/+package+/static
           
           creating build/lib/pyramid/scaffolds/starter/+package+/templates
           
           copying pyramid/scaffolds/starter/+package+/templates/mytemplate.pt_tmpl -> build/lib/pyramid/scaffolds/starter/+package+/templates
           
           creating build/lib/pyramid/scaffolds/zodb
           
           copying pyramid/scaffolds/zodb/CHANGES.txt_tmpl -> build/lib/pyramid/scaffolds/zodb
           
           copying pyramid/scaffolds/zodb/MANIFEST.in_tmpl -> build/lib/pyramid/scaffolds/zodb
           
           copying pyramid/scaffolds/zodb/README.txt_tmpl -> build/lib/pyramid/scaffolds/zodb
           
           copying pyramid/scaffolds/zodb/development.ini_tmpl -> build/lib/pyramid/scaffolds/zodb
           
           copying pyramid/scaffolds/zodb/production.ini_tmpl -> build/lib/pyramid/scaffolds/zodb
           
           copying pyramid/scaffolds/zodb/setup.cfg_tmpl -> build/lib/pyramid/scaffolds/zodb
           
           copying pyramid/scaffolds/zodb/setup.py_tmpl -> build/lib/pyramid/scaffolds/zodb
           
           creating build/lib/pyramid/scaffolds/zodb/+package+
           
           copying pyramid/scaffolds/zodb/+package+/__init__.py -> build/lib/pyramid/scaffolds/zodb/+package+
           
           copying pyramid/scaffolds/zodb/+package+/models.py -> build/lib/pyramid/scaffolds/zodb/+package+
           
           copying pyramid/scaffolds/zodb/+package+/tests.py_tmpl -> build/lib/pyramid/scaffolds/zodb/+package+
           
           copying pyramid/scaffolds/zodb/+package+/views.py_tmpl -> build/lib/pyramid/scaffolds/zodb/+package+
           
           creating build/lib/pyramid/scaffolds/zodb/+package+/static
           
           copying pyramid/scaffolds/zodb/+package+/static/favicon.ico -> build/lib/pyramid/scaffolds/zodb/+package+/static
           
           copying pyramid/scaffolds/zodb/+package+/static/footerbg.png -> build/lib/pyramid/scaffolds/zodb/+package+/static
           
           copying pyramid/scaffolds/zodb/+package+/static/headerbg.png -> build/lib/pyramid/scaffolds/zodb/+package+/static
           
           copying pyramid/scaffolds/zodb/+package+/static/ie6.css -> build/lib/pyramid/scaffolds/zodb/+package+/static
           
           copying pyramid/scaffolds/zodb/+package+/static/middlebg.png -> build/lib/pyramid/scaffolds/zodb/+package+/static
           
           copying pyramid/scaffolds/zodb/+package+/static/pylons.css -> build/lib/pyramid/scaffolds/zodb/+package+/static
           
           copying pyramid/scaffolds/zodb/+package+/static/pyramid-small.png -> build/lib/pyramid/scaffolds/zodb/+package+/static
           
           copying pyramid/scaffolds/zodb/+package+/static/pyramid.png -> build/lib/pyramid/scaffolds/zodb/+package+/static
           
           copying pyramid/scaffolds/zodb/+package+/static/transparent.gif -> build/lib/pyramid/scaffolds/zodb/+package+/static
           
           creating build/lib/pyramid/scaffolds/zodb/+package+/templates
           
           copying pyramid/scaffolds/zodb/+package+/templates/mytemplate.pt -> build/lib/pyramid/scaffolds/zodb/+package+/templates
           
           creating build/lib/pyramid/tests/fixtures
           
           copying pyramid/tests/fixtures/components.mak -> build/lib/pyramid/tests/fixtures
           
           copying pyramid/tests/fixtures/hello_inherit_pkg.mak -> build/lib/pyramid/tests/fixtures
           
           copying pyramid/tests/fixtures/hellocompo.mak -> build/lib/pyramid/tests/fixtures
           
           copying pyramid/tests/fixtures/helloinherit.mak -> build/lib/pyramid/tests/fixtures
           
           copying pyramid/tests/fixtures/helloworld.mak -> build/lib/pyramid/tests/fixtures
           
           copying pyramid/tests/fixtures/helloworld.mako -> build/lib/pyramid/tests/fixtures
           
           copying pyramid/tests/fixtures/layout.mak -> build/lib/pyramid/tests/fixtures
           
           copying pyramid/tests/fixtures/minimal.pt -> build/lib/pyramid/tests/fixtures
           
           copying pyramid/tests/fixtures/minimal.txt -> build/lib/pyramid/tests/fixtures
           
           copying pyramid/tests/fixtures/nonminimal.mak -> build/lib/pyramid/tests/fixtures
           
           copying pyramid/tests/fixtures/nonminimal.txt -> build/lib/pyramid/tests/fixtures
           
           copying pyramid/tests/fixtures/pp.pt -> build/lib/pyramid/tests/fixtures
           
           copying pyramid/tests/fixtures/withmacro.pt -> build/lib/pyramid/tests/fixtures
           
           creating build/lib/pyramid/tests/fixtures/static
           
           copying pyramid/tests/fixtures/static/.hiddenfile -> build/lib/pyramid/tests/fixtures/static
           
           copying pyramid/tests/fixtures/static/arcs.svg.tgz -> build/lib/pyramid/tests/fixtures/static
           
           Traceback (most recent call last):
           
             File "<string>", line 1, in <module>
           
             File "/app/build/pyramid/setup.py", line 122, in <module>
           
               """
           
             File "/app/.heroku/python/lib/python3.3/distutils/core.py", line 148, in setup
           
               dist.run_commands()
           
             File "/app/.heroku/python/lib/python3.3/distutils/dist.py", line 917, in run_commands
           
               self.run_command(cmd)
           
             File "/app/.heroku/python/lib/python3.3/distutils/dist.py", line 936, in run_command
           
               cmd_obj.run()
           
             File "/app/.heroku/python/lib/python3.3/site-packages/distribute-0.6.34-py3.3.egg/setuptools/command/install.py", line 53, in run
           
               return _install.run(self)
           
             File "/app/.heroku/python/lib/python3.3/distutils/command/install.py", line 569, in run
           
               self.run_command('build')
           
             File "/app/.heroku/python/lib/python3.3/distutils/cmd.py", line 313, in run_command
           
               self.distribution.run_command(command)
           
             File "/app/.heroku/python/lib/python3.3/distutils/dist.py", line 936, in run_command
           
               cmd_obj.run()
           
             File "/app/.heroku/python/lib/python3.3/distutils/command/build.py", line 126, in run
           
               self.run_command(cmd_name)
           
             File "/app/.heroku/python/lib/python3.3/distutils/cmd.py", line 313, in run_command
           
               self.distribution.run_command(command)
           
             File "/app/.heroku/python/lib/python3.3/distutils/dist.py", line 936, in run_command
           
               cmd_obj.run()
           
             File "/app/.heroku/python/lib/python3.3/site-packages/distribute-0.6.34-py3.3.egg/setuptools/command/build_py.py", line 90, in run
           
               self.build_package_data()
           
             File "/app/.heroku/python/lib/python3.3/site-packages/distribute-0.6.34-py3.3.egg/setuptools/command/build_py.py", line 150, in build_package_data
           
               outf, copied = self.copy_file(srcfile, target)
           
             File "/app/.heroku/python/lib/python3.3/distutils/cmd.py", line 348, in copy_file
           
               dry_run=self.dry_run)
           
             File "/app/.heroku/python/lib/python3.3/distutils/file_util.py", line 102, in copy_file
           
               if not os.path.isfile(src):
           
             File "/app/.heroku/python/lib/python3.3/genericpath.py", line 29, in isfile
           
               st = os.stat(path)
           
           UnicodeEncodeError: 'ascii' codec can't encode character '\xe9' in position 31: ordinal not in range(128)
           
           ----------------------------------------
           Command /app/.heroku/python/bin/python -c "import setuptools;__file__='/app/build/pyramid/setup.py';exec(compile(open(__file__).read().replace('\r\n', '\n'), __file__, 'exec'))" install --single-version-externally-managed --record /tmp/pip-a7sbnh-record/install-record.txt failed with error code 1 in /app/build/pyramid
           Storing complete log in /app/.pip/pip.log
     !     Heroku push rejected, failed to compile Python app

    To git@heroku.com:pyramid-python-3.git
     ! [remote rejected] master -> master (pre-receive hook declined)
    error: failed to push some refs to 'git@heroku.com:pyramid-python-3.git'


Debug
=====

::

    aclark@Alexs-MacBook-Pro:~/Developer/pyramid_python_3/ > heroku run bash                    
    Running `bash` attached to terminal... up, run.7917
    ~ $ echo $LANG

    ~ $ 

Should be: en_US.UTF-8
