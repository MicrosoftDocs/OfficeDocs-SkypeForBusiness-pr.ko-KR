---
title: 프론트 엔드 컴퓨터 추가
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndMachinePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e7fe2522-1bd2-416a-9dbb-51cacea9c6e0
ROBOTS: NOINDEX, NOFOLLOW
description: 이 풀에 프런트 엔드 서버로 추가 하려는 각 컴퓨터의 FQDN (정규화 된 도메인 이름)을 지정 합니다. 목록에 컴퓨터를 추가한 후에는 토폴로지를 게시하기 전에 언제든지 컴퓨터의 FQDN을 업데이트하거나 풀에서 제거할 수 있습니다. 토폴로지를 게시 한 후 FQDN을 변경 하려면 토폴로지 작성기에서 서버를 삭제 한 다음 새 FQDN을 사용 하 여 풀에 새 서버를 추가 해야 합니다. 토폴로지에 프런트 엔드 풀을 추가 하는 방법에 대 한 자세한 내용은 배포 설명서에서 프런트 엔드 풀 정의 및 구성을 참조 하세요.
ms.openlocfilehash: a4ff4ce7a7fc775e33657dc2f8602d62163ed1d4
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41798545"
---
# <a name="add-front-end-machine"></a>프론트 엔드 컴퓨터 추가

이 풀에 프런트 엔드 서버로 추가 하려는 각 컴퓨터의 FQDN (정규화 된 도메인 이름)을 지정 합니다. 목록에 컴퓨터를 추가한 후에는 토폴로지를 게시하기 전에 언제든지 컴퓨터의 FQDN을 업데이트하거나 풀에서 제거할 수 있습니다. 토폴로지를 게시 한 후 FQDN을 변경 하려면 토폴로지 작성기에서 서버를 삭제 한 다음 새 FQDN을 사용 하 여 풀에 새 서버를 추가 해야 합니다. 토폴로지에 프런트 엔드 풀을 추가 하는 방법에 대 한 자세한 내용은 배포 설명서에서 [프런트 엔드 풀 정의 및 구성을](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) 참조 하세요.

> [!IMPORTANT]
> 토폴로지 작성기는 풀에 프런트 엔드 서버를 20 개까지 포함할 수 있음을 나타냅니다. 지원 되는 최대 서버 수는 12 개입니다. 패브릭에 정의 된 최대 20 개의 statefull 서버를 보유할 수 있으며, 여기에서 12 개는 언제 든 지 활성화 및 온라인 상태가 될 수 있습니다.


