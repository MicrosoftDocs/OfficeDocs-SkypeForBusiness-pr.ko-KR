---
title: 2013에서 AlwaysOn 가용성 그룹을 사용하여 데이터베이스 비즈니스용 Skype 서버
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 026c4469-f471-4e4f-a77d-a7d22a925e5a
description: '요약: 기존 AlwaysOn 가용성 그룹에 비즈니스용 Skype 서버 데이터베이스를 더 추가하는 방법을 알아보고, 비즈니스용 Skype 서버에서 AlwaysOn 가용성 그룹의 일부인 백 엔드 서버를 패치하거나 업그레이드한 후 필요한 추가 단계에 대해 비즈니스용 Skype 서버.'
---

# <a name="manage-databases-with-an-alwayson-availability-group-in-skype-for-business-server"></a>2013에서 AlwaysOn 가용성 그룹을 사용하여 데이터베이스 비즈니스용 Skype 서버

이 문서의 단계를 사용하여 비즈니스용 Skype 서버의 기존 AlwaysOn 가용성 그룹에 비즈니스용 Skype 서버 데이터베이스를 더 추가하고, 비즈니스용 Skype 서버에서 AlwaysOn 가용성 그룹의 일부인 백 엔드 서버를 패치하거나 업그레이드한 후 필요한 추가 단계에 대해 비즈니스용 Skype 서버.

## <a name="add-databases-to-an-alwayson-availability-group"></a>AlwaysOn 가용성 그룹에 데이터베이스 추가 

1. 사용자 SQL Server Management Studio 열고 AlwaysOn 가용성 그룹으로 이동합니다. 주 복제 데이터베이스로 장애 조치(fail over)합니다.
    
2. 토폴로지 작성기에서 AlwaysOn SQL Server 그룹의 FQDN을 해당 그룹의 기본 노드의 FQDN으로 설정합니다.
    
   - 토폴로지 작성기 열기, 기존 배포에서 토폴로지 **다운로드를 선택한** 다음 확인을 **클릭합니다**.
    
   - 사용자 비즈니스용 Skype 서버 확장하고 토폴로지, 저장소 **SQL Server 확장합니다**. 새 AlwaysOn SQL 저장소를 마우스 오른쪽 단추로 클릭하고 속성 **편집을 클릭합니다**.
    
   - 페이지 아래쪽의 SQL Server **FQDN** 상자에 AlwaysOn 가용성 그룹의 기본 노드의 FQDN을 입력합니다.
    
3. 토폴로지를 게시합니다. 작업 **메뉴에서** 토폴 **로지와** 게시를 **클릭합니다**. 그런 다음 확인 페이지에서 다음을 **클릭합니다**.
    
4. 이 SQL Server Management Studio 사용하여 AlwaysOn 가용성 그룹에 새 데이터베이스를 추가합니다.
    
## <a name="patch-or-update-a-sql-server-in-an-alwayson-availability-group"></a>AlwaysOn 가용성 SQL Server 패치 또는 업데이트

AlwaysOn 가용성 그룹의 일부인 백 엔드 서버를 패치한 후 토폴로지 다시 게시해야 합니다.

1. 서버 또는 서버에 비즈니스용 Skype 설치합니다.
    
2. 비즈니스용 Skype 관리 셸에서 다음 PowerShell 명령을 실행합니다(SQL AlwaysOn 데이터베이스에 변경 내용을 적용할 수 있는 권한이 있는 계정으로 로그인).
    
    ```PowerShell
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn [sqlpool.contoso.com] -Verbose
    ```

    여기서 [sqlpool.contoso.com]는 AlwaysOn 가용성 그룹의 FQDN(FQDN)으로 대체됩니다.
