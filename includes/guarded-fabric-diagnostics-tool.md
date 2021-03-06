> [!Note] 
> Quando a ferramenta de diagnóstico Malha Protegida (Get-HgsTrace -RunDiagnostics) for executada, o status incorreto poderá ser retornado informando que a configuração HTTPS foi rompida, quando, na verdade, não foi rompida ou não está sendo utilizada. Esse erro pode ser retornado independentemente do modo de atestado do HGS. Estas são as causas possíveis:
>
> - O HTTPS foi, de fato, configurado incorretamente/rompido<br>
> - Você está usando atestado confiável de administrador e a relação de confiança está quebrada<br>
> &nbsp;&nbsp;&nbsp;&nbsp;-Isso é independente de o HTTPS estar configurado corretamente, de forma inadequada ou não estar em uso.<br>
>
> Observe que o diagnóstico só retornará esse status incorreto quando um host Hyper-V for direcionado. Se o diagnóstico estiver direcionando o Serviço Guardião de Host, o status retornado será correto.

<!-- Appears in guarded-fabric-setting-up-the-host-guardian-service-hgs.md and guarded-fabric-troubleshoot-diagnostics.md
-->
