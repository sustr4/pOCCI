OCCI Compliance Tests Matrix
============================

.. role:: ok

.. role:: fail

.. role:: good

.. raw:: html

   <style>
     .ok {color:green}
     .good {color:orange}
     .fail {color:red}
   </style>

+-------------------------------------+-------------------------------------------------------------------------+
|                                     |                               rOCCI server                              |
+-------------------------------------+--------------+---------------------+------------------------------------+
|                                     |     dummy    |      OpenNebula     |             Amazon EC2             |
+=====================================+==============+=====================+====================================+
| OCCI/CORE/DISCOVERY/001             |   :ok:`OK`   |       :ok:`OK`      |              :ok:`OK`              |
+-------------------------------------+--------------+---------------------+------------------------------------+
| OCCI/CORE/DISCOVERY/001             |   :ok:`OK`   |       :ok:`OK`      |              :ok:`OK`              |
+-------------------------------------+--------------+---------------------+------------------------------------+
| OCCI/CORE/READ/001                  |   :ok:`OK`   |       :ok:`OK`      |              :ok:`OK`              |
+-------------------------------------+--------------+---------------------+------------------------------------+
| OCCI/CORE/READ/002                  |   :ok:`OK`   |       :ok:`OK`      |              :ok:`OK`              |
+-------------------------------------+--------------+---------------------+------------------------------------+
| OCCI/CORE/CREATE/001 [tpl]_         |      --      |          --         |                 --                 |
+-------------------------------------+--------------+---------------------+------------------------------------+
| OCCI/CORE/CREATE/006 [nip]_         |      --      |          --         |                 --                 |
+-------------------------------------+--------------+---------------------+------------------------------------+
| OCCI/CORE/DELETE/001 [comp]_ [del]_ | :good:`GOOD` |     :good:`GOOD`    |        :good:`GOOD` [del2]_        |
+-------------------------------------+--------------+---------------------+------------------------------------+
| OCCI/CORE/UPDATE/001 [comp]_        |   :ok:`OK`   | :fail:`FAIL` [upd]_ |         :fail:`FAIL` [nip]_        |
+-------------------------------------+--------------+---------------------+------------------------------------+
| OCCI/INFRA/CREATE/001               |   :ok:`OK`   | :fail:`FAIL` [tpl]_ |         :fail:`FAIL` [tpl]_        |
+-------------------------------------+--------------+---------------------+------------------------------------+
| OCCI/INFRA/CREATE/002               |   :ok:`OK`   |       :ok:`OK`      | :good:`GOOD` [volsiz]_  [volsiz2]_ |
+-------------------------------------+--------------+---------------------+------------------------------------+
| OCCI/INFRA/CREATE/003               |   :ok:`OK`   | :fail:`FAIL` [net]_ |        :fail:`FAIL` [net2]_        |
+-------------------------------------+--------------+---------------------+------------------------------------+
| OCCI/INFRA/CREATE/004               |   :ok:`OK`   |       :ok:`OK`      |              :ok:`OK`              |
+-------------------------------------+--------------+---------------------+------------------------------------+
| OCCI/INFRA/CREATE/005 [tpl]_        |      --      |          --         |                 --                 |
+-------------------------------------+--------------+---------------------+------------------------------------+
| OCCI/INFRA/CREATE/006               |   :ok:`OK`   | :good:`GOOD` [run]_ |              :ok:`OK`              |
+-------------------------------------+--------------+---------------------+------------------------------------+
| OCCI/INFRA/CREATE/007               |   :ok:`OK`   | :good:`GOOD` [run]_ |        :fail:`FAIL` [net3]_        |
+-------------------------------------+--------------+---------------------+------------------------------------+

Notes
-----

.. [comp] existing compute instance required [**all**]

.. [del] different behaviour on not existing instances [**OpenNebula**, **dummy**]

.. [del2] deletion delayed [**EC2**]

.. [net] network management support not implemented [**OpenNebula**]

.. [net2] creating networks has been disabled [**EC2**]

.. [net3] VPC networks cannot be attached to existing instances! [**EC2**]

.. [nip] not implemented [**all**]

.. [run] requires running instannes during hotplug [**OpenNebula**]

.. [tpl] os_tpl mixin required [**all**]

.. [upd] partial implementation in rOCCI [**OpenNebula**]

.. [volsiz] volume size limit (too small in compliance tests) [**EC2**]

.. [volsiz2] float not supported [**EC2**]

