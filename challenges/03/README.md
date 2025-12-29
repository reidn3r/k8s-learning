### Nível 3 - Volumes**
#### 9. Crie um pod com volume persistente (PVC) de 1GB

#### 10. Escreva um arquivo dentro do pod no volume

#### 11. Delete o pod e crie outro montando o mesmo PVC - o arquivo deve estar lá

---

### Conceitos Fundamentais de Armazenamento no Kubernetes

### **1. PV — PersistentVolume**

O **PV** é um recurso de armazenamento do cluster.
Ele representa uma “fatia de disco” já provisionada

**Características:**

* Define **capacidade**, **modo de acesso** e **fonte de armazenamento** (hostPath, EBS, NFS etc.).
* Existe **independentemente de pods e PVCs**.

---

### **2. PVC — PersistentVolumeClaim**

O **PVC** é uma solicitação de armazenamento feita por um usuário/app

**Características:**

* Define **quanto de recurso** é necessário e **qual o modo de acesso** (RWO, ROX, RWX).
* O Kubernetes busca um PV compatível e faz o **binding** automático.
* O Pod só é capaz de usar volume por mio de um PVC

---

### Observações

* Após o binding, um **PV fica reservado exclusivamente ao PVC** até que o PVC seja removido.
* Pods usam volumes somente via PVC.
* Reiniciar ou recriar um pod não apaga os dados, pois eles estão no PV, não no container.
* A política de retenção é definida no PV via persistentVolumeReclaimPolicy:

  * Retain: Dados continuam mesmo após excluir o PVC.
  * Delete: PV e dados são apagados junto com PVC.