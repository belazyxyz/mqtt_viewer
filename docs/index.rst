.. mu_mqtt documentation master file, created by
   sphinx-quickstart on Sun Aug 30 03:00:07 2020.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

Welcome to mu_mqtt's documentation!
=================================

mu_mqtt created to view the MQTT broker messages

.. toctree::
   :maxdepth: 2
   :caption: Contents:



Usage
==================

.. code-block:: python

   from mutcm import TCMParser

   tcm = TCMParser('cases')
   print(tcm.case_runs)
   # this should returns the JSON object with all runs

   @pytest.mark.parametrize("data", tcm.case_runs)
   def test_api(data):
      print(data)
      assert tcm.api_test(data) == data['expected']