---
name: Custom issue template
about: Describe this issue template's purpose here.
title: "\\STS"
labels: documentation
assignees: sts192111

---

#	#
# include (AddCXXCompilerFlag)	# include (AddCXXCompilerFlag)
# add_cxx_compiler_flag (-Wall)	# add_cxx_compiler_flag (-Wall)
# add_cxx_compiler_flag (-no-strict-aliasing RELEASE)	# add_cxx_compiler_flag (-no-strict-aliasing RELEASE)
# يتطلب CMake 2.6+	# يتطلب CMake 2.6+
إذا (__add_cxx_compiler_flag)	إذا (__add_cxx_compiler_flag)
  عودة ()	  عودة ()
endif ()	endif ()
مجموعة (__add_cxx_compiler_flag المدرجة)	مجموعة (__add_cxx_compiler_flag المدرجة)
تشمل (CheckCXXCompilerFlag)	تشمل (CheckCXXCompilerFlag)
الوظيفة (mangle_compiler_flag FLAG OUTPUT )	الوظيفة (mangle_compiler_flag FLAG OUTPUT )
  سلسلة ( TOUPPER  "HAVE_CXX_FLAG_ $ {FLAG} " SANITIZED_FLAG)	  سلسلة ( TOUPPER  "HAVE_CXX_FLAG_ $ {FLAG} " SANITIZED_FLAG)
  سلسلة ( REPLACE  "+"  "X" SANITIZED_FLAG $ {SANITIZED_FLAG} )	  سلسلة ( REPLACE  "+"  "X" SANITIZED_FLAG $ {SANITIZED_FLAG} )
  سلسلة ( REGEX  REPLACE  "[^ A-Za-z_0-9]"  "_" SANITIZED_FLAG $ {SANITIZED_FLAG} )	  سلسلة ( REGEX  REPLACE  "[^ A-Za-z_0-9]"  "_" SANITIZED_FLAG $ {SANITIZED_FLAG} )
  سلسلة ( REGEX  REPLACE  "_ +"  "_" SANITIZED_FLAG $ {SANITIZED_FLAG} )	  سلسلة ( REGEX  REPLACE  "_ +"  "_" SANITIZED_FLAG $ {SANITIZED_FLAG} )
  مجموعة ( $ {OUTPUT}  " $ {  SANITIZED_FLAG } " PARENT_SCOPE )	  مجموعة ( $ {OUTPUT}  " $ {  SANITIZED_FLAG } " PARENT_SCOPE )
وظيفة النهاية (mangle_compiler_flag)	وظيفة النهاية (mangle_compiler_flag)


الوظيفة (add_cxx_compiler_flag FLAG)	الوظيفة (add_cxx_compiler_flag FLAG)
  سلسلة ( REPLACE  "-Wno-"  "-W" MAIN_FLAG $ {FLAG} )	  سلسلة ( REPLACE  "-Wno-"  "-W" MAIN_FLAG $ {FLAG} )
  mangle_compiler_flag ( " $ {MAIN_FLAG} "  MANGLED_FLAG )	  mangle_compiler_flag ( " $ {MAIN_FLAG} "  MANGLED_FLAG_NAME )
  إذا (تم تحديد CMAKE_REQUIRED_FLAGS)	  إذا (تم تحديد CMAKE_REQUIRED_FLAGS)
    مجموعة (OLD_CMAKE_REQUIRED_FLAGS " $ {CMAKE_REQUIRED_FLAGS} " )	    مجموعة (OLD_CMAKE_REQUIRED_FLAGS " $ {CMAKE_REQUIRED_FLAGS} " )
    مجموعة (CMAKE_REQUIRED_FLAGS " $ {CMAKE_REQUIRED_FLAGS}  $ {FLAG} " )	    مجموعة (CMAKE_REQUIRED_FLAGS " $ {CMAKE_REQUIRED_FLAGS}  $ {FLAG} " )
  آخر ()	  آخر ()
    مجموعة (CMAKE_REQUIRED_FLAGS " $ {FLAG} " )	    مجموعة (CMAKE_REQUIRED_FLAGS " $ {FLAG} " )
  endif ()	  endif ()
  check_cxx_compiler_flag ( " $ {MAIN_FLAG} "  $ { MANGLED_FLAG } )	  check_cxx_compiler_flag ( " $ {MAIN_FLAG} "  $ { MANGLED_FLAG_NAME } )
  إذا (تم تحديد OLD_CMAKE_REQUIRED_FLAGS)	  إذا (تم تحديد OLD_CMAKE_REQUIRED_FLAGS)
    مجموعة (CMAKE_REQUIRED_FLAGS " $ {OLD_CMAKE_REQUIRED_FLAGS} " )	    مجموعة (CMAKE_REQUIRED_FLAGS " $ {OLD_CMAKE_REQUIRED_FLAGS} " )
  آخر ()	  آخر ()
    غير محدّد (CMAKE_REQUIRED_FLAGS)	    غير محدّد (CMAKE_REQUIRED_FLAGS)
  endif ()	  endif ()
  إذا ( MANGLED_FLAG )	  إذا ( {MANGLED_FLAG_NAME} دولار )
    مجموعة (VARIANT $ {ARGV1} )	    مجموعة (VARIANT $ {ARGV1} )
    إذا ( ARGV1 )	    إذا ( ARGV1 )
      سلسلة ( TOUPPER  "_ $ {VARIANT} " VARIANT)	      سلسلة ( TOUPPER  "_ $ {VARIANT} " VARIANT)
-53،12 +53،12endfunction ()


الوظيفة (add_required_cxx_compiler_flag FLAG)	الوظيفة (add_required_cxx_compiler_flag FLAG)
  سلسلة ( REPLACE  "-Wno-"  "-W" MAIN_FLAG $ {FLAG} )	  سلسلة ( REPLACE  "-Wno-"  "-W" MAIN_FLAG $ {FLAG} )
  mangle_compiler_flag ( " $ {MAIN_FLAG} "  MANGLED_FLAG )	  mangle_compiler_flag ( " $ {MAIN_FLAG} "  MANGLED_FLAG_NAME )
  مجموعة (OLD_CMAKE_REQUIRED_FLAGS " $ {CMAKE_REQUIRED_FLAGS} " )	  مجموعة (OLD_CMAKE_REQUIRED_FLAGS " $ {CMAKE_REQUIRED_FLAGS} " )
  مجموعة (CMAKE_REQUIRED_FLAGS " $ {CMAKE_REQUIRED_FLAGS}  $ {FLAG} " )	  مجموعة (CMAKE_REQUIRED_FLAGS " $ {CMAKE_REQUIRED_FLAGS}  $ {FLAG} " )
  check_cxx_compiler_flag ( " $ {MAIN_FLAG} "  $ { MANGLED_FLAG } )	  check_cxx_compiler_flag ( " $ {MAIN_FLAG} "  $ { MANGLED_FLAG_NAME } )
  مجموعة (CMAKE_REQUIRED_FLAGS " $ {OLD_CMAKE_REQUIRED_FLAGS} " )	  مجموعة (CMAKE_REQUIRED_FLAGS " $ {OLD_CMAKE_REQUIRED_FLAGS} " )
  إذا ( MANGLED_FLAG )	  إذا ( {MANGLED_FLAG_NAME} دولار )
    مجموعة (VARIANT $ {ARGV1} )	    مجموعة (VARIANT $ {ARGV1} )
    إذا ( ARGV1 )	    إذا ( ARGV1 )
      سلسلة ( TOUPPER  "_ $ {VARIANT} " VARIANT)
