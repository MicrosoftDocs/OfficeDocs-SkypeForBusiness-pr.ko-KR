---
title: ClientVersions 보기
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: caf7678f-83a0-46c8-83cc-fee4c3991f52
description: ClientVersions 보기에는 데이터베이스에 기록되는 세션에 참여한 다양한 클라이언트 유형 및 버전 정보가 저장되어 있습니다. 보기의 각 레코드는 하나의 클라이언트 버전을 나타냅니다. 이 보기는 Microsoft Lync Server 2013에서 도입했습니다.
---

# <a name="clientversions-view"></a>ClientVersions 보기
 
ClientVersions 보기에는 데이터베이스에 기록되는 세션에 참여한 다양한 클라이언트 유형 및 버전 정보가 저장되어 있습니다. 보기의 각 레코드는 하나의 클라이언트 버전을 나타냅니다. 이 보기는 Microsoft Lync Server 2013에서 도입했습니다.
  
> [!NOTE]
> 특정 열에 여러 레코드가 있을 수 있습니다. 
  
|**열**|**데이터 형식**|**세부 정보**|
|:-----|:-----|:-----|
|**VersionId** <br/> |int  <br/> |이 클라이언트 유형 및 버전을 식별하는 고유 번호입니다.  <br/> |
|**버전** <br/> |nvarchar(256)  <br/> |사용자 에이전트를 나타냅니다.  <br/> |
|**ClientType** <br/> |int  <br/> |클라이언트 유형입니다  <br/> |
|**ClientCategory** <br/> |nvarchar(64)  <br/> |클라이언트가 속한 범주입니다. 예를 들어 Conferencing_Attendant_1.0 클라이언트는 ClientCategory CAA에 속합니다.  <br/> |
   

