![imagen](https://github.com/user-attachments/assets/f2e1fa69-429e-499c-95e3-f957ac55f754)# aws-cdk-playground-python

El objetivo es preparar el entorno para trabajar con AWS CDK con Python.

## Instalación y preparación de AWS CDK

1. En caso de no tener nodejs, instalar con asdf:
```bash
   asdf plugin add nodejs https://github.com/asdf-vm/asdf-nodejs.git
   asdf install nodejs 22.11.0
```
<p align="center">
  <img width='60%' src="https://github.com/alvarodelburgoperez/AWS-CDK/blob/main/assets/asdf.png" />
</p>


3. Verificar la instalación:
   ```bash
   cdk --version
   ```
<p align="center">
  <img width='60%' src="https://github.com/alvarodelburgoperez/TERRAFORM/blob/main/assets/cdk.png" />
</p>



4. Preparar el directorio del proyecto:
   ```bash
   mkdir cdk-iam-lab
   cd cdk-iam-lab
   ```

<p align="center">
  <img width='60%' src="https://github.com/alvarodelburgoperez/TERRAFORM/blob/main/assets/mkdir.png" />
</p>


5. Inicializar proyecto CDK con Python:
   ```bash
   cdk init app --language python
   ```
<p align="center">
  <img width='60%' src="https://github.com/alvarodelburgoperez/TERRAFORM/blob/main/assets/cdk-init.png" />
</p>


6. Inicializad el entorno de CDK en vuestra cuenta de AWS:
   ```bash
   cdk bootstrap
   ```
<p align="center">
  <img width='60%' src="https://github.com/alvarodelburgoperez/TERRAFORM/blob/main/assets/bootstrap.png" />
</p>


7. Instalar dependencias del proyecto:
   ```bash
   pip install -r requirements.txt
   ```
<p align="center">
  <img width='60%' src="https://github.com/alvarodelburgoperez/TERRAFORM/blob/main/assets/paso7.png" />
</p>


## Creación de Usuario IAM y Grupo con AWS CDK

El objetivo es crear un usuario IAM con permisos de PowerUserAccess usando CDK con Python.

1. Reemplazar el contenido de `cdk_iam_lab/cdk_iam_lab_stack.py` con el fichero de este repositorio


   ```python
   from aws_cdk import (
       Stack,
       CfnOutput,
       aws_iam as iam
   )
   from constructs import Construct

   class CdkIamLabStack(Stack):
       def __init__(self, scope: Construct, construct_id: str, **kwargs) -> None:
           ...

   ```

2. Sintetizar el template CloudFormation:
   ```bash
   cd ..
   cdk synth > cf.yaml
   ```
<p align="center">
  <img width='60%' src="https://github.com/alvarodelburgoperez/TERRAFORM/blob/main/assets/sintetizar.png" />
</p>


3. Desplegar la infraestructura:
   ```bash
   cdk deploy
   ```
<p align="center">
  <img width='60%' src="https://github.com/alvarodelburgoperez/TERRAFORM/blob/main/assets/deploy.png" />
</p>

4. Descomentad el output y volved a desplegar para ver un update.

<p align="center">
  <img width='60%' src="https://github.com/alvarodelburgoperez/TERRAFORM/blob/main/assets/paso4.png" />
</p>

TRas borrar el user groups de AWS a mano:

<p align="center">
  <img width='60%' src="https://github.com/alvarodelburgoperez/TERRAFORM/blob/main/assets/deploy2.png" />
</p>

5. Capturar los outputs del despliegue con los detalles del usuario

<p align="center">
  <img width='60%' src="https://github.com/alvarodelburgoperez/TERRAFORM/blob/main/assets/ouput1.png" />
</p>

<p align="center">
  <img width='60%' src="https://github.com/alvarodelburgoperez/TERRAFORM/blob/main/assets/ouput2.png" />
</p>

6. Enviar un email al profesor con:
   - Captura del despliegue correcto
   - Evidencia de la creación del usuario y grupo en la consola de AWS
   - URL al repositorio con el código en github

Referencias:
- [AWS CDK Python Reference](https://docs.aws.amazon.com/cdk/api/v2/python/)
- [CDK Workshop for Python](https://cdkworkshop.com/30-python.html)

