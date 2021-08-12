---
title: 프론트 엔드 컴퓨터 추가
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndMachinePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e7fe2522-1bd2-416a-9dbb-51cacea9c6e0
description: 이 풀에 프런트 엔드 서버로 추가할 각 컴퓨터의 FQDN(정규화된 도메인 이름)을 지정합니다. 목록에 컴퓨터를 추가한 후 토폴로지를 게시하기 전에 언제든지 컴퓨터의 FQDN을 업데이트하거나 풀에서 해당 컴퓨터를 제거할 수 있습니다. 토폴로지를 게시한 후 FQDN을 변경하려면 토폴로지 작성기에서 서버를 삭제한 다음 풀에 새 FQDN으로 새 서버를 추가해야 합니다. 토폴로지에 프런트 엔드 풀을 추가하는 데 대한 자세한 내용은 배포 설명서에서 Define and Configure a Front End Pool을 참조하십시오.
ms.openlocfilehash: 912b4599db1882fda9741573ce1ac2637584ca84990d54ca3964037f4e00d396
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54342153"
---
# <a name="add-front-end-machine"></a>프론트 엔드 컴퓨터 추가

이 풀에 프런트 엔드 서버로 추가할 각 컴퓨터의 FQDN(정규화된 도메인 이름)을 지정합니다. 목록에 컴퓨터를 추가한 후 토폴로지를 게시하기 전에 언제든지 컴퓨터의 FQDN을 업데이트하거나 풀에서 해당 컴퓨터를 제거할 수 있습니다. 토폴로지를 게시한 후 FQDN을 변경하려면 토폴로지 작성기에서 서버를 삭제한 다음 풀에 새 FQDN으로 새 서버를 추가해야 합니다. 토폴로지에 프런트 엔드 풀을 추가하는 데 대한 자세한 내용은 배포 설명서에서 [Define and Configure a Front End Pool을](/previous-versions/office/lync-server-2013/lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server) 참조하십시오.

> [!IMPORTANT]
> 토폴로지 작성기에서는 풀에 최대 20대의 프런트 엔드 서버를 사용할 수 있습니다. 지원되는 최대 서버 수는 12개입니다. 패브릭에 정의된 상태 저장 서버를 최대 20개까지 사용할 수 있으며, 이 중 12대는 한 번만 활성 상태 및 온라인 상태일 수 있습니다.