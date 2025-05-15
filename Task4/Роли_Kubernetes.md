| Роль  | Права роли | Группы пользователей |
| --- | --- | --- |
| Название роли, которое отвечает требованиям RBAC в Kubernets. | Укажите права, которые необходимо выдать этой роли. | Выделите группы пользователей в организации, которые нужно связать с этой ролью. |
|ClusterRole: cluster-pods-reader|"pods","pods/log" - "get", "list", "watch"|DevOps-инженера, ИБ специалист|
|ClusterRole: cluster-pods-writer|"pods" - "create", "update", "patch","delete"|DevOps-инженер ответственный за билд|
|ClusterRole: cluster-secrets-writer|"secrets" - "get", "list", "watch","create", "update", "patch","delete"|DevOps-инженер ответственный за билд|
|ClusterRole: cluster-deployments-writer|"deployments","replicasets" - "get", "list", "watch","create", "update", "patch","delete"|DevOps-инженер ответственный за деплой|
|ClusterRole: cluster-roles-writer|"roles","clusterroles" - "get", "list", "watch","create", "update", "patch","delete"|DevOps-инженер ответственный за ИБ|
|ClusterRole: cluster-networkpolicies-writer|"networkpolicies" - "get", "list", "watch","create", "update", "patch","delete"|DevOps-инженер ответственный за ИБ|
|Role: client-pods-reader|"pods","pods/log" - "get", "list", "watch"|Инженера по эксплуатации, Разработчики домена продаж|
|Role: tenant-pods-reader|"pods","pods/log" - "get", "list", "watch"|Инженера по эксплуатации, Разработчики домена ЖКУ|
|Role: finans-pods-reader|"pods","pods/log" - "get", "list", "watch"|Инженера по эксплуатации, Разработчики домена финансов|
|Role: databi-pods-reader|"pods","pods/log" - "get", "list", "watch"|Инженера по эксплуатации, Разработчики домена Дата|

