---
title: 영구 채팅 서버 테이블 목록
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 26c9e271-3516-4d90-b930-70fec4e359ea
description: 영구 채팅 데이터베이스 schema는 다음 테이블로 구성됩니다.
ms.openlocfilehash: 2d5accc32b01c4c854fc3603e4ec3c1dc61a115b
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58606037"
---
# <a name="list-of-persistent-chat-server-tables"></a>영구 채팅 서버 테이블 목록
 
영구 채팅 데이터베이스 schema는 다음 테이블로 구성됩니다.
  
## <a name="active-directory-sync"></a>Active Directory 동기화

|**표**|**설명**|
|:-----|:-----|
|[tblADCookie](tbladcookie.md) <br/> |현재 LDAP(Lightweight Directory Access Protocol) 동기화 쿠키를 포함 각 행은 영구 채팅 서버가 변경 내용을 적극적으로 모니터링하는 Active Directory 도메인 서비스 도메인에 해당합니다. 이 표에는 영구 채팅 서버와 관련된 Active Directory 도메인만 표시됩니다.  <br/> |
|[tblPrincipalMemberDifference](tblprincipalmemberdifference.md) <br/> |이후 Active Directory 동기화 단계에서 아직 처리되지 않은 그룹 구성원 변경 내용(구성원 추가 및 제거됨)을 포함하며 Active Directory 동기화의 첫 번째 단계에서 사용되는 임시 테이블(tblADUpdates 테이블과 함께) 중 하나입니다.  <br/> 멤버 자격 변경은 tblPrincipal 테이블에 나열되거나 이미 구성원이 목록에 있는 그룹에 한해 저장, 처리 또는 둘 다에 해당합니다.  <br/> |
|[tblADUpdates](tbladupdates.md) <br/> |이후 Active Directory 동기화 단계에서 아직 처리되지 않은 Active Directory 도메인 서비스에 대한 변경 내용을 포함하며 Active Directory 동기화의 첫 번째 단계에서 사용되는 임시 테이블(tblPrincipalMemberDifference 테이블과 함께) 중 하나입니다.  <br/> Active Directory에 대한 변경 내용은 이미 tblPrincipal 테이블에 나열된 사용자에 한해 저장, 처리 또는 둘 다에 해당합니다.  <br/> |
|[tblPrincipalMembers](tblprincipalmembers.md) <br/> |보안 주체 멤버 자격이 들어 있습니다.  <br/> |
|[tblPrincipalMeta](tblprincipalmeta.md) <br/> |Active Directory에서 새로 고쳐야 하는 보안 주체가 들어 있습니다.  <br/> |
|[tblSkippedAffiliations](tblskippedaffiliations.md) <br/> |보통 Active Directory 액세스 오류로 인해 새로 고칠 수 없는 소속 정보가 들어 있습니다.  <br/> 이 표는 정보 제공 목적으로만 사용됩니다. 해당 콘텐츠는 사용되지 않습니다.  <br/> 제대로 새로 고칠 수 없는 소속이 있는 보안 주체는 tblPrincipalMeta 테이블에 유지될 수 있으며 새로 고칠 수 있는 기회가 다시 부여됩니다.  <br/> |
   
## <a name="principals-affiliations-nodes-scopes-and-roles"></a>보안 주체, 소속, 노드, 범위 및 역할

|**표**|**설명**|
|:-----|:-----|
|[tblPrincipalType](tblprincipaltype.md) <br/> |tblPrincipal 테이블에 있는 항목의 범주를 분류하는 보안 주체 유형이 들어 있습니다. 이 테이블은 정적입니다. 데이터베이스를 만들 때 설정하며 변경되지 않습니다.  <br/> |
|[tblPrincipal](tblprincipal.md) <br/> |모든 사용자(사용자, 폴더, 그룹 등)가 들어 있습니다. 영구 채팅 서버는 이를 이기종의 플랫 목록으로 처리합니다. 다양한 열은 각 보안 주체의 유형을 기반으로 합니다.  <br/> 이러한 보안 주체는 대부분 Active Directory에 저장된 개체의 캐시된 복사본입니다. 이러한 Active Directory 개체의 Principal 테이블에 캐시된 복사본을 만드는 것은 프로비전이라고 합니다.  <br/> 일부 보안 주체는 다른 보안 주체보다 적극적으로 만들어지며 일부 Active Directory 개체는 모두 무시됩니다.  <br/> |
|[tblPrincipalAffiliations](tblprincipalaffiliations.md) <br/> |Active Directory 보안 그룹, Active Directory 컨테이너 등에서 멤버 자격을 설명하는 보안 주체 회원 정보가 들어 있습니다.  <br/> |
|[tblNode](tblnode.md) <br/> |제어판에서 관리되는 범주 노드를 포함  <br/> |
|[tblRoleType](tblroletype.md) <br/> |역할 유형 및 관련 권한 집합이 들어 있습니다. 이 lookup table is static.  <br/> |
|[tblScopePrincipal](tblscopeprincipal.md) <br/> |노드에 할당된 범위가 들어 있습니다.  <br/> |
|[tblPrincipalRole](tblprincipalrole.md) <br/> |노드에 할당된 역할이 들어 있습니다.  <br/> |
|[tblSiopWhiteList](tblsiopwhitelist.md) <br/> |노드와 연결될 수 있는 등록된 추가 기능을 포함  <br/> |
|[tblEnumAttribute](tblenumattribute.md) <br/> |tblNode 테이블에 사용되는 하드코드된 "표시 여부" 및 "동작" 특성만 들어 있습니다.  <br/> |
|[tblEnumValue](tblenumvalue.md) <br/> |tblNode 테이블에 사용되는 하드코드된 "Visibility" 및 "Behavior" 특성의 값을 포함  <br/> |
   
## <a name="invites-chats-and-other-client-support"></a>초대, 채팅 및 기타 클라이언트 지원

|**표**|**설명**|
|:-----|:-----|
|[tblPrincipalInvites](tblprincipalinvites.md) <br/> |자동 초대가 사용하도록 설정된 모든 노드에 대해 시스템의 모든 프로비전된 사용자에 대한 초대가 들어 있습니다.  <br/> |
|[tblChat](tblchat.md) <br/> |모든 채팅 메시지가 들어 있습니다.  <br/> |
|[tblLastInviteId](tbllastinviteid.md) <br/> |각 사용자에 대해 생성되어 tblPrincipalInvites 테이블에 사용된 마지막 초대 ID가 들어 있습니다.  <br/> |
|[tblLastChatId](tbllastchatid.md) <br/> |각 사용자에 대해 생성되어 tblChat 테이블에 사용된 마지막 채팅 ID가 들어 있습니다.  <br/> |
|[tblPreference](tblpreference.md) <br/> |사용자 클라이언트 기본 설정(레거시 클라이언트에서만 사용)이 들어 있습니다.  <br/> |
|[tblFileToken](tblfiletoken.md) <br/> |파일 전송을 위한 임시 토큰이 들어 있습니다. 파일을 업로드하거나 다운로드할 때마다 영구 채팅 서비스는 클라이언트가 웹 서비스 파일 저장소에 액세스하는 데 사용하는 토큰을 생성합니다.  <br/> |
   
## <a name="server-support"></a>서버 지원

|**표**|**설명**|
|:-----|:-----|
|[tblServerIdentity](tblserveridentity.md) <br/> |영구 채팅 서버 풀의 활성 서버가 들어 있습니다.  <br/> |
|[tblAdminLock](tbladminlock.md) <br/> |일부 관리자 명령을 실행하기 위해 관리자 잠금이 포함되어 있습니다. tblSystemRevision 테이블의 시스템 개정 항목은 잠금이 릴리스될 때마다 증분됩니다.  <br/> |
|[tblSystemRevision](tblsystemrevision.md) <br/> |여러 서버에서 일관성을 유지하기 위해 tblAdminLock 테이블과 함께 사용되는 변경 번호 항목이 들어 있습니다.  <br/> |
|[tblActivePeers](tblactivepeers.md) <br/> |영구 채팅 서비스 간의 현재 피어 투 피어 연결이 들어 있습니다.  <br/> |
|[tblConfig](tblconfig.md) <br/> |영구 채팅 서버 지원되지 않는 구성이 들어 있습니다.  <br/> |
   

