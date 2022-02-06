---
title: 데이터베이스 만들기
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
  - CSH
ms.custom:
  - ms.lync.tb.PublishTopologyCreateDatabasePage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 4d391619-1cab-4265-ae8a-2519993705bc
description: 토폴로지 작성기에서는 데이터베이스를 저장소에 설치하는 SQL Server 있습니다. 토폴로지 작성기에서 데이터베이스를 설치할 때 응용 프로그램은 토폴로지의 정보를 읽은 다음 지정된 컴퓨터 또는 SQL Server 클러스터에 필요한 SQL Server 설치합니다. 이는 토폴로지 작성기를 사용하여 사용 가능한 유일한 데이터베이스 설치 유형입니다. 특정 컴퓨터에 특정 데이터베이스를 설치해야 하는 경우 또는 함께 있는 데이터베이스를 설치해야 하는 경우 명령줄 인터페이스와 Windows PowerShell cmdlet을 Install-CsDatabase 합니다.
---

# <a name="create-database"></a>데이터베이스 만들기
 
토폴로지 작성기에서는 데이터베이스를 저장소에 설치하는 SQL Server 있습니다. 토폴로지 작성기에서 데이터베이스를 설치할 때 응용 프로그램은 토폴로지의 정보를 읽은 다음 지정된 컴퓨터 또는 SQL Server 클러스터에 필요한 SQL Server 설치합니다. 이는 토폴로지 작성기를 사용하여 사용 가능한 유일한 데이터베이스 설치 유형입니다. 특정 컴퓨터에 특정 데이터베이스를 설치해야 하는 경우 또는 함께 제공된 데이터베이스를 설치해야 하는 경우 명령줄 Windows PowerShell [Install-CsDatabase](/powershell/module/skype/install-csdatabase?view=skype-ps) cmdlet을 대신 사용해야 합니다.
  
### <a name="creating-a-database"></a>데이터베이스 만들기

1. 비즈니스용 Skype 서버 노드를 클릭한 다음 데이터베이스 설치 **를 클릭합니다**.
    
2. 데이터베이스 **설치** 대화 상자의 데이터베이스 만들기 페이지에서 새 데이터베이스  를 만들 SQL Server 저장소의 FQDN(FQDN)을 선택합니다.
    
3. **고급** 을 클릭합니다. **데이터베이스 파일 위치 선택** 대화 상자에서 다음 옵션 중 하나를 선택합니다.
    
   - **데이터베이스 파일 위치 자동 지정**. 이 옵션을 선택하는 경우 토폴로지 작성기에서 기본 제공 알고리즘을 사용하여 데이터베이스 로그 및 데이터 파일의 저장 위치를 선택합니다.
    
   - **SQL Server 인스턴스 기본값 사용**. 이 옵션을 선택하면 기본 제공 알고리즘이 데이터베이스 로그 및 데이터 파일의 저장 위치를 선택하는 데 사용되지 않습니다. 대신 로그 및 데이터 파일은 SQL Server 경로에 지정된 위치에 저장됩니다(이러한 경로는 SQL Server 관리자가 고급에서 구성해야 합니다). 데이터 파일은 기본 SQL Server 파일 위치에 저장되고 로그 파일은 기본 로그 파일 위치에 SQL Server 저장됩니다.
    
4. **확인** 을 클릭합니다.
    
5. **데이터베이스 만들기** 페이지에서 **다음** 을 클릭합니다.
    
6. **데이터베이스 생성 완료** 페이지에서 **마침** 을 클릭합니다.
