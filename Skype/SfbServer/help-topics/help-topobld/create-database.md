---
title: 데이터베이스 작성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.PublishTopologyCreateDatabasePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d391619-1cab-4265-ae8a-2519993705bc
description: 토폴로지 작성기는 SQL Server store에 데이터베이스를 설치 하는 방법을 제공 합니다. 토폴로지 작성기를 사용 하 여 데이터베이스를 설치 하는 경우 응용 프로그램은 토폴로지에서 정보를 읽은 다음 지정 된 SQL Server 컴퓨터 또는 SQL Server 클러스터에 필요한 데이터베이스를 설치 합니다. 이는 토폴로지 작성기를 사용하여 사용 가능한 유일한 데이터베이스 설치 유형입니다. 특정 컴퓨터에 특정 데이터베이스를 설치 해야 하거나 collocated 데이터베이스를 설치 해야 하는 경우 Windows PowerShell 명령줄 인터페이스와 설치-CsDatabase cmdlet을 대신 사용 해야 합니다.
ms.openlocfilehash: cd3bd6e24f0dc3ec21c5cfa8626d9696454855e7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41820240"
---
# <a name="create-database"></a>데이터베이스 작성
 
토폴로지 작성기는 SQL Server store에 데이터베이스를 설치 하는 방법을 제공 합니다. 토폴로지 작성기를 사용 하 여 데이터베이스를 설치 하는 경우 응용 프로그램은 토폴로지에서 정보를 읽은 다음 지정 된 SQL Server 컴퓨터 또는 SQL Server 클러스터에 필요한 데이터베이스를 설치 합니다. 이는 토폴로지 작성기를 사용하여 사용 가능한 유일한 데이터베이스 설치 유형입니다. 특정 컴퓨터에 특정 데이터베이스를 설치 해야 하거나 collocated 데이터베이스를 설치 해야 하는 경우 Windows PowerShell 명령줄 인터페이스와 [설치-csdatabase](https://docs.microsoft.com/powershell/module/skype/install-csdatabase?view=skype-ps) cmdlet을 대신 사용 해야 합니다.
  
### <a name="creating-a-database"></a>데이터베이스 만들기

1. 비즈니스용 Skype 서버 2015 노드를 클릭 한 다음 **데이터베이스 설치**를 클릭 합니다.
    
2. 데이터베이스 **설치** 대화 상자의 **데이터베이스 만들기** 페이지에서 새 데이터베이스를 만들 SQL Server 저장소의 FQDN (정규화 된 도메인 이름)을 선택 합니다.
    
3. **고급**을 클릭합니다. **데이터베이스 파일 위치 선택** 대화 상자에서 다음 옵션 중 하나를 선택합니다.
    
   - **데이터베이스 파일 위치 자동 지정**. 이 옵션을 선택하는 경우 토폴로지 작성기에서 기본 제공 알고리즘을 사용하여 데이터베이스 로그 및 데이터 파일의 저장 위치를 선택합니다.
    
   - **SQL Server 인스턴스 기본값을 사용**합니다. 이 옵션을 선택 하면 기본 제공 알고리즘이 데이터베이스 로그 및 데이터 파일의 저장소 위치를 선택 하는 데 사용 되지 않습니다. 대신 로그 및 데이터 파일은 SQL Server 기본 경로에 지정 된 위치에 저장 됩니다 (이 경로는 SQL Server 관리자가 고급으로 구성 해야 함). 기본 sql server 로그 파일 위치에 로그 파일이 저장 되는 동안 데이터 파일은 기본 SQL Server 데이터 파일 위치에 저장 됩니다.
    
4. **확인**을 클릭합니다.
    
5. **데이터베이스 만들기** 페이지에서 **다음**을 클릭합니다.
    
6. **데이터베이스 생성 완료** 페이지에서 **마침**을 클릭합니다.
    

