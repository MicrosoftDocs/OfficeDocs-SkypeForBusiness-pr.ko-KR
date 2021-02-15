---
title: 인증서 요청(기본)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployCertRequestBasics
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 2c6b40d5-207a-4ca9-a090-e43350f4968f
ROBOTS: NOINDEX, NOFOLLOW
description: 이름 및 보안 설정 페이지에는 이름 정의 텍스트 상자, 개인 키와 공개 키 쌍의 비트 길이에 대한 드롭다운 목록 및 인증서의 개인 키를 내보낼 수 있는 것으로 표시하는 확인란이 있습니다.
ms.openlocfilehash: 5ae91c6fbe1c84d0fee0486dec0ca2efd9717e10
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830418"
---
# <a name="certificate-request-basic"></a><span data-ttu-id="016c2-103">인증서 요청(기본)</span><span class="sxs-lookup"><span data-stu-id="016c2-103">Certificate Request (Basic)</span></span>
 
<span data-ttu-id="016c2-104">이름 **및** 보안 설정 페이지에는 이름 정의 텍스트 **상자,** 개인 키와 공개 키 쌍의 비트 길이에 대한 드롭다운 목록 및 인증서의 개인 키를 내보낼 수 있는 것으로 표시하는 확인란이 **있습니다.** </span><span class="sxs-lookup"><span data-stu-id="016c2-104">The **Name and Security Settings** page provides a text box to define a **Friendly Name**, a drop-down list for the **Bit length** of the private and public key pair, and a check box that enables you to **Mark the certificate's private key as exportable**.</span></span>
  
<span data-ttu-id="016c2-105">인증서의 이름(단순한 이름)은 간편하게 인지할 수 있는 이름으로, 인증서를 보는 사용자가 보다 쉽게 이름을 식별할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="016c2-105">The friendly, or simple, name on a certificate is an easily recognizable name that makes it easier for the person who views the certificate to identify it.</span></span>
  
<span data-ttu-id="016c2-106">개인 키와 공개 키 쌍의 비트 길이는 1024, 2048 또는 4096으로 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="016c2-106">The Bit length of the private and public key pair can be selected as 1024, 2048, or 4096.</span></span>
  
<span data-ttu-id="016c2-107">인증서의 개인 키를  내보낼 수 있는 것으로 표시하기 위한 확인란을 선택하면 인증서 및 개인 키를 다른 컴퓨터나 서버로 내보내고 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="016c2-107">Selecting the check box for **Mark the certificate's private key as exportable** allows the certificate and private key to be exported and moved to another computer or server.</span></span> <span data-ttu-id="016c2-108">이 경우 MRAS(미디어 릴레이 인증 서비스)에 대한 에지 서버 풀을 만들 때만 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="016c2-108">The only time that this is required is when you are creating a pool of Edge Servers for the media relay authentication service (MRAS).</span></span>
  
> [!CAUTION]
> <span data-ttu-id="016c2-109">인증서 및 키 쌍의 보안을 유지하려면 반드시 필요한 경우 인증서의 개인 키를 내보낼 수 있는 것으로 표시 옵션을 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="016c2-109">To help maintain the security of the certificate and the key pair, you should select the Mark the certificate's private key as exportable option only if it is absolutely necessary.</span></span> 
  

