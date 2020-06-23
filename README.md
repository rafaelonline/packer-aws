# Images Packer para AWS

Repo criado para armazenar códigos Packer para AWS

## Pré-Requisitos

Packer instalado, consulte a [documentação oficial](https://learn.hashicorp.com/packer/getting-started/install) em caso de dúvidas.

[Shared Credentials file](https://www.packer.io/docs/builders/amazon#shared-credentials-file) configurado. Veja como instalar o AWS CLI através da [documentação oficial](https://docs.aws.amazon.com/pt_br/cli/latest/userguide/cli-chap-welcome.html).

```bash
[default]
aws_access_key_id=<your access key id>
aws_secret_access_key=<your secret access key>
```

Permissão adequada na AWS para criar os recursos, consulte o documento [IAM Task or Instance Role](https://www.packer.io/docs/builders/amazon#iam-task-or-instance-role).

Utilizaremos o [Ansible](https://docs.ansible.com/ansible/latest/index.html) como [Provisioner](https://www.packer.io/docs/provisioners/ansible)

## Executando

Atualize o arquivo de variáveis. Exemplo:

```json
{
  "profile": "customprofile",
  "region": "us-east-1",
  "name": "iamgem123"
}
```
No mesmo nível dos arquivos, execute:
```bash
$ packer build -var-file='variables.json' packer.json
````
## Contribuição

Pull requests são bem-vindos. 

## Roadmap

:mag: Adicionar outras versões de sistema operacional.

:wrench: Melhorar como o Ansible está sendo executado. Utilizar Ansible Galaxy

## Licença

Este projeto está licenciado sob a licença Apache 2.0 - consulte o arquivo [LICENSE](https://github.com/rafaelonline/packer-aws/blob/master/LICENSE) para obter mais detalhes.
