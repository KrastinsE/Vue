<template>
    <nav class="navbar navbar-expand-lg bg-secondary text-uppercase fixed-" id="mainNav">
        <div class="container">
            <a class="navbar-brand" href="#page-refresh">Market View</a>
            <button class="navbar-toggler navbar-toggler-right text-uppercase font-weight-bold bg-primary text-white rounded" type="button" data-toggle="collapse" data-target="#navbarResponsive" aria-controls="navbarResponsive" aria-expanded="false" aria-label="Toggle navigation">
                User
                <i class="fas fa-bars"></i>
            </button>
            <div class="collapse navbar-collapse" id="navbarResponsive">
                <ul class="navbar-nav ml-auto">
                     <div class="btn-group-open">
                        <a class="btn btn-primary" href="#my-user-profile"><i class="fa fa-user fa-fw"></i> User</a>
                        <a class="btn btn-primary" data-toggle="dropdown-toggle" href="#user-control-panel">
                             <span class="fa fa-caret-down" title="Toggle dropdown menu"></span>
                        </a>
                        <div class="dropdown-menu">
                            <li><a href="#"><i class="fa fa-pencil fa-fw"></i>Log in</a></li>
                            <li><a href="#"><i class="fa fa-trash-o fa-fw"></i>Setting</a></li>
                        </div>
                    </div>
                </ul>
            </div>
        </div>
    </nav>
</template>

<script>
export default {
    
}
</script>

<style lang="css">

</style>