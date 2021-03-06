include_directories ("${PROJECT_SOURCE_DIR}/lib")

add_library(corct-support summarize_command_line.cc)

set(APPS_LIBRARIES
  corct
  corct-support
  clangTooling
  ${TINFO_LIB}
  z
  c
)

macro(add_coarct_exe app_name app_src)
  add_executable(${app_name} ${app_src} )
  target_link_libraries(${app_name} ${APPS_LIBRARIES} )
endmacro()

add_coarct_exe(callsite-lister CallsiteLister.cc)

add_coarct_exe(function-lister FuncLister.cc)

add_coarct_exe(function-mover FunctionMover.cc )

add_coarct_exe(template-vars-report TemplateVarFinder.cc )

add_coarct_exe(temp-type-report TemplateType.cc )

add_coarct_exe(function-printer FunctionPrinter.cc )

add_coarct_exe(typedef-report TypedefFinder.cc )

add_coarct_exe(global-replace GlobalReplace.cc )

add_coarct_exe(struct-field-use StructFieldUser.cc )

add_coarct_exe(func-decl-lister-rav FuncListerRAV.cc )

add_coarct_exe(func-decl-lister-am FuncListerAM.cc )

add_coarct_exe(global-detect-hasGlobalStorage GlobalDetect_hasGlobalStorage.cc )

add_coarct_exe(global-detect-hasLocalQualifiers GlobalDetect_hasLocalQualifiers.cc )

add_coarct_exe(global-detect-hasLocalStorage GlobalDetect_hasLocalStorage.cc )

add_coarct_exe(global-detect-hasStaticStorageDuration GlobalDetect_hasStaticStorageDuration.cc )

add_coarct_exe(global-detect-isStaticStorageClass GlobalDetect_isStaticStorageClass.cc )

add_coarct_exe(list-member-calls ListCXXMemberCalls.cc )

# add_coarct_exe(while-loop-detect WhileLoopFinder.cc )

# add_coarct_exe(loop-convert LoopConvert.cpp

# End of file
